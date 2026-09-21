---
name: coruma-sync-status
description: Check whether the authenticated user's Coruma devices are connected, which health categories are authorized, and when data last synchronized. Use for freshness and connection troubleshooting.
---

# Coruma synchronization status

Call `get_sync_status` when the user asks whether Coruma is connected, which categories an agent may read, or when data last synchronized.

Report device status, server time, authorized categories, and freshness in plain language. A successful device sync does not prove every Apple Health category is permitted or every record has arrived.

If authorization is missing, tell the user to reconnect Coruma and select the required category. Do not ask the user to paste access tokens, passwords, one-time codes, screenshots of health records, or raw health payloads into the conversation.
