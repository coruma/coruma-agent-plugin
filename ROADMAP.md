# Distribution roadmap

## 0.1 — Portable package

- [x] Portable Agent Plugin manifest
- [x] Codex compatibility manifest
- [x] Remote MCP configuration
- [x] Read-only health summary, workout review, and sync-status skills
- [x] Positive, indirect-discovery, negative, and failure test prompts
- [x] Public security and privacy guidance

## Production readiness

- [ ] Publish final privacy notice with controller contact
- [ ] Publish a public support contact
- [ ] Publish terms of service
- [ ] Prepare a synthetic reviewer account without MFA or email/SMS confirmation
- [ ] Add explicit MCP output schemas and per-tool OAuth security schemes
- [ ] Add `openWorldHint: false` to every Coruma MCP tool
- [ ] Verify OAuth challenges and scope upgrades in each target client
- [ ] Run the discovery prompt suite against every target client

## Distribution order

1. Cursor Marketplace and Grok Bot
2. Grok Build Marketplace
3. Official MCP Registry
4. Claude distribution channels
5. OpenAI universal plugin directory, after policy and legal review for health data

Marketplace submissions and announcements remain separate release actions. A repository release does not imply that a marketplace has reviewed or endorsed Coruma.
