# Turnstile pilot backup

Created before enabling Cloudflare Turnstile on the pilot form at `/application/`.

Files:

- `include-index-index_form_inc.php.before` — live `/include/index/index_form_inc.php`
- `local-ajax-add_project_form.php.before` — live `/local/ajax/add_project_form.php`
- `include-index-index_form_inc.php.before-managed-fix` — pilot form immediately before switching the widget from Invisible to Managed mode

The Cloudflare secret key is intentionally not stored in this repository. The server file `/bitrix/php_interface/turnstile_config.php` did not exist before the pilot.

Rollback: restore both `.before` files to their original live paths and clear the Bitrix cache.
