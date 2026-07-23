# Python Host Skeleton

This directory describes the intended shape of an MCP-aware Nephew host. It is deliberately framework-neutral until a specific MCP SDK and runtime are selected.

```text
python-host-skeleton/
├── main.py                 # reception and interface entry point
├── host.py                 # application lifecycle and client ownership
├── directors/
│   └── planner.py          # mission planning
├── managers/
│   └── dispatcher.py       # work orders, permissions, routing
├── workers/
│   ├── research.py
│   ├── writing.py
│   └── publishing.py
├── mcp/
│   ├── client_pool.py      # one logical client connection per server
│   ├── registry.py         # server definitions and capability mapping
│   ├── policy.py           # allowlists and approval checks
│   └── types.py            # internal request/result models
├── brains/
│   └── router.py           # chooses local or remote model
├── memory/
│   ├── conversations.py
│   └── retrieval.py
├── governance/
│   ├── identity.yaml
│   ├── bylaws.md
│   └── rules/
├── skills/
├── prompts/
├── tools/
├── config/
│   └── host.yaml
└── tests/
```

## Pseudocode

```python
async def handle_mission(raw_input: str, actor: Actor) -> MissionResult:
    mission = reception.normalize(raw_input, actor)
    governance_context = governance.load_for(mission)
    plan = await directors.create_plan(mission, governance_context)

    work_orders = managers.create_work_orders(plan)
    results = []

    for order in work_orders:
        managers.authorize(order, actor)
        worker = workers.select(order)
        result = await worker.execute(
            order=order,
            brains=brain_router,
            memory=memory_service,
            capabilities=mcp_client_pool,
        )
        results.append(result)

    final = await directors.review_and_synthesize(mission, plan, results)
    audit.record(mission, plan, results, final)
    return reception.present(final)
```

## Client pool concept

```python
class MCPClientPool:
    """Host-owned collection of logical client-to-server connections."""

    async def call_tool(self, server_id: str, tool: str, arguments: dict):
        policy.authorize(server_id=server_id, capability=tool, arguments=arguments)
        client = await self.get_or_connect(server_id)
        return await client.call_tool(tool, arguments)
```

The worker requests a capability through a controlled host service. It does not receive a raw credential or unrestricted server object.
