# Request Lifecycle

## Example mission

> Inspect a GitHub repository, summarize its open issues, and save the report to WordPress.

## End-to-end flow

1. **Interface receives the mission**
   - CLI, GUI, voice, mobile, or inbound API accepts the request.

2. **Reception normalizes it**
   - creates a request ID
   - records requester identity and channel
   - validates basic syntax
   - forwards a normalized mission object

3. **Directors consult governance**
   - identity and mission
   - bylaws and rules
   - skills and system prompts
   - available brains, workers, tools, and servers
   - approval requirements

4. **Directors produce a plan**
   - read repository metadata
   - list open issues
   - summarize findings
   - draft WordPress content
   - request approval before publishing if policy requires it

5. **Managers create work orders**
   - assign GitHub research worker
   - assign writing worker
   - assign WordPress publishing worker
   - set budgets, timeouts, permissions, and dependencies

6. **Worker requests a capability**
   - the GitHub worker requests `list_open_issues`
   - the request goes through management policy checks

7. **Host selects the correct client instance**
   - server registry maps the capability to the GitHub MCP connection

8. **Client initializes or reuses a connection**
   - transport connects
   - protocol version and capabilities are negotiated
   - server tool list is known

9. **Client builds an MCP tool call**
   - tool name
   - validated arguments
   - request ID
   - optional progress and tracing metadata

10. **Server receives and authorizes it**
    - authenticates connection when required
    - verifies scopes and repository boundaries
    - validates arguments

11. **Server invokes implementation**
    - may call GitHub REST/GraphQL APIs or a local Git operation

12. **Server returns a structured result**
    - content
    - metadata
    - protocol error if unsuccessful

13. **Client correlates and parses the response**
    - matches response to request
    - classifies errors
    - records metrics and audit data

14. **Worker completes its scoped task**
    - converts raw issue data into a worker result

15. **Managers coordinate dependencies**
    - pass evidence to writing worker
    - validate that claims are grounded
    - send draft to publishing worker after approval

16. **Directors inspect completion**
    - compare results with mission and success criteria
    - determine whether to retry, revise, or finish

17. **Reception formats the final response**
    - returns a human-readable status through the originating interface

## Result flow

```text
Provider system
      ^      |
      |      v
MCP Server -> MCP Client -> Worker -> Manager -> Director -> Reception -> Interface
```

## Failure flow

At every stage, errors should be transformed into a structured record containing:
- stage
- request/work-order ID
- machine-readable error code
- safe human-readable message
- retryability
- remediation suggestion
- redacted diagnostics

## Approval points

Typical human approval gates include:
- publishing content
- sending messages
- deleting or overwriting data
- spending money
- modifying repositories
- running privileged shell commands
- exposing private records
