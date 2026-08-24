# Cloudflare Turnstile pilot for the KEO request form

Date: 2026-08-24

Scope: only `https://solargy.kz/application/`.

## Backup and rollback point

- Backup commit: `0fcd4a5`
- Branch: `codex/private-wide-backup`
- Original `/include/index/index_form_inc.php`: `backups/2026-08-24-turnstile-keo-pilot/include-index-index_form_inc.php.before`
- Original `/local/ajax/add_project_form.php`: `backups/2026-08-24-turnstile-keo-pilot/local-ajax-add_project_form.php.before`
- `/bitrix/php_interface/turnstile_config.php` did not exist before the pilot.

## Live changes

- Created an Invisible Cloudflare Turnstile widget for `solargy.kz`.
- Added `/bitrix/php_interface/turnstile_config.php` on the server for the private secret key.
- The secret key is not stored in Git, page markup, JavaScript, or this log.
- Replaced the visible CAPTCHA only on `/application/` with an invisible Turnstile execution flow.
- Added server-side Siteverify validation and an allowed-hostname check for `solargy.kz` and `www.solargy.kz`.
- Added Bitrix session validation, a honeypot field, a minimum form-fill time, and server-side checks for required fields and email format on the pilot route.
- Preserved the legacy CAPTCHA path for all non-pilot instances of the shared form.

## Verification

- `/application/` loads without a PHP fatal error.
- The page has one Turnstile container, one pilot button, and no legacy project-form CAPTCHA image.
- The Turnstile client script is present.
- The custom AJAX handler loads and returns valid JSON on a read-only GET syntax check.
- Other shared-form instances continue to use their legacy CAPTCHA path.
- No customer form was submitted during verification.
- One unrelated existing console warning remains: Yandex Maps reports an invalid API key.

## Rollback

1. Restore the two `.before` files to their original live paths.
2. Delete `/bitrix/php_interface/turnstile_config.php` from the server.
3. Clear the Bitrix cache.
4. Disable or delete the Turnstile widget in Cloudflare if it is no longer needed.
