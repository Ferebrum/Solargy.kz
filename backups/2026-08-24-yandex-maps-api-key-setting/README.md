# Backup: Yandex Maps API key setting

- Date: 2026-08-24
- System: Bitrix module `fileman`
- Option: `yandex_map_api_key`
- State before change: empty (no API key configured)
- Secret values: intentionally not stored in Git

## Rollback

Open Bitrix administration:

`Settings -> Product settings -> Module settings -> Site structure management`

Clear the field `Yandex Maps API key` and save the module settings. This restores the recorded pre-change state.

The Yandex Maps developer-console key is a separate external resource. Disabling or deleting it is not required to roll back the website setting.
