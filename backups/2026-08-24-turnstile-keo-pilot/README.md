# Turnstile pilot backup

Created before enabling Cloudflare Turnstile on the pilot form at `/application/`.

Files:

- `include-index-index_form_inc.php.before` — live `/include/index/index_form_inc.php`
- `local-ajax-add_project_form.php.before` — live `/local/ajax/add_project_form.php`

The Cloudflare secret key is intentionally not stored in this repository.

Rollback: restore both `.before` files to their original live paths and clear the Bitrix cache.
