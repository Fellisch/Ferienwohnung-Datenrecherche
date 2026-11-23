---
name: database-research
description: Use the internal Database MCP tools for read-only research in Homesapi or Homesdata, including finding tables, inspecting fields and checking specific records.
---

# Database research

Use the `trfewo-database-mcp` tools for targeted, read-only data research.

1. Choose `homesapi` or `homesdata` as the required `schema` on every database tool call. The older aliases `apiv3` and `hoteldata` are also accepted. Separate connections require separate queries.
2. Discover tables with `list_tables` and inspect relevant columns with `describe_table` before writing SQL. Do not guess names or relationships.
3. Use a filtered, bounded read-only query through `execute_query`. Select only fields needed for the question and add a suitable `LIMIT`. The server rejects writes and unsupported statements.
4. Report the finding in plain language. Mention uncertainty, incomplete results, and any truncation. Avoid returning personal data beyond what the question requires.

If authorization or database access fails, report the tool error. Do not suggest bypassing authentication or SQL validation.
