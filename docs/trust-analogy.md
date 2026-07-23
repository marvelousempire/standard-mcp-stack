# Trust Architecture Analogy

This analogy is a learning model for the Standard MCP Stack. It is not legal advice and does not claim that software roles are legally equivalent to trust roles.

## Role map

| Software architecture | Trust/company analogy | Responsibility |
|---|---|---|
| Requester | Beneficiary or authorized third party | States a need or requests records/work |
| Interface | Website, phone, mail, reception channel | Provides a way to contact the trust |
| `main.py` / controller | Reception desk | Receives, identifies, timestamps, and routes the request |
| Directors | Board or strategic trustees | Interpret mission and create a plan |
| Governance documents | Trust instrument, bylaws, handbook | Define identity, purpose, authority, rules, style, and boundaries |
| Managers | Managing trustees | Turn plans into work orders, control assets, permissions, and vendors |
| Workers | Contractors and specialists | Perform scoped work |
| Brains | Advisers and subject-matter experts | Reason, draft, classify, code, or analyze |
| Memory | Trust records and operating history | Preserve continuity |
| Knowledge | Archive, deeds, manuals, source documents | Supply evidence and reference material |
| Tools | Equipment and deterministic systems | Perform concrete actions |
| Credentials | Membership card, badge, signature authority | Prove identity or delegated authority |
| MCP host | Trust office/company headquarters | Contains the organizational system |
| MCP client | Communications capability operated by the office | Speaks MCP to a particular provider |
| MCP protocol | Standard communication forms and language | Defines how messages are formatted and exchanged |
| MCP request | Completed requisition or work-order form | States the capability and arguments requested |
| MCP server | Provider service desk | Publishes available services and receives standardized requests |
| Provider API | Provider's internal counter/register/system | Performs provider-specific operations |
| VPN/TLS | Secured road or sealed communication channel | Protects data in transit |
| Audit log | Trust ledger and receipts | Records who requested, approved, executed, and received work |

## Example: purchasing supplies

1. A beneficiary asks the trust to repair a property.
2. Reception records the request.
3. Directors consult the trust instrument and produce a repair plan.
4. A managing trustee creates a scoped work order for a contractor.
5. The contractor identifies needed supplies and requests them from management.
6. Management verifies budget, permission, and vendor policy.
7. The host uses the MCP client connected to the vendor MCP server.
8. The client sends an MCP tool call containing the requested item details.
9. Authentication proves the trust account; authorization limits what it may buy.
10. The MCP server calls the vendor's internal API or order system.
11. The result returns through the MCP server and client.
12. Management records the receipt and gives the contractor the approved supplies.
13. The contractor completes the work and reports the result.
14. Results flow back through management, directors, reception, and finally the requester.

## Important corrections to the analogy

- The MCP client is not the credential. The credential is used by the client.
- The MCP request is not the client. It is the message built and sent by the client.
- The secure network connection is not the API. TLS or a VPN protects transport; an API defines provider operations.
- The server can be inside or outside the organization.
- A host normally manages multiple client instances to connect to multiple servers.
- A server can expose local functionality without calling any external API.
