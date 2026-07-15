# Mufal Meetings for Codex

This plugin connects Codex to a user's Mufal Cloud account through OAuth and a read-only MCP server. It turns every Mufal project into a dated context layer made from its goal, durable memory, linked meetings, structured notes, actions, speakers, transcripts, and saved meeting chats.

It exposes six tools:

- list and filter cloud-synced meetings;
- retrieve a complete meeting and transcript;
- search transcripts across all projects;
- list projects with meeting counts and date coverage;
- retrieve a complete, dated project timeline;
- search evidence inside a specific project.

Local-only meetings and local-only project documents are not available until the supported data is synced to Mufal Cloud.

Production MCP URL: `https://admin.mufal.com/api/mcp`

Product page: <https://mufal.com/mufal-for-codex>

After installing, connect a Mufal account when Codex prompts for authentication, then start a new task. See [MANUAL.md](./MANUAL.md) for setup, prompt examples, privacy details, and troubleshooting.
