# Yandex Maps JavaScript API key connection

Date: 2026-08-24

## Scope

- Connected Yandex Maps JavaScript API in the Yandex developer console.
- Payer country: Russia (confirmed by the site owner).
- Tariff: free with restrictions, `0 RUB`.
- Renamed the generated key to `Solargy.kz — карта сайта`.
- Restricted the key by HTTP Referer to `solargy.kz` (subdomains are included by Yandex).
- Stored the key in the Bitrix `fileman` module option `yandex_map_api_key`.
- No secret value is stored in this repository.

## Backup and rollback

- Pre-change state and rollback instructions: `backups/2026-08-24-yandex-maps-api-key-setting/README.md`.
- Backup commit created before the Bitrix change: `3fdaabe`.
- Rollback: clear `Yandex Maps API key` in the Bitrix Site Structure Management module settings and save.

## Verification

- `https://solargy.kz/contacts/` returned HTTP 200.
- Public HTML contains the Yandex Maps 2.1 loader with a non-empty 36-character API key.
- The public contacts page rendered the interactive Yandex map and its controls.
- Yandex console reports the key as active.

## Notes

- Yandex states that new keys and HTTP Referer restrictions may take up to 15 minutes to propagate fully.
- The free plan shown in the console allows 100 Panorama API calls per day. The website should be monitored for actual usage before considering a paid plan.
