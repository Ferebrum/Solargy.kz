# Client confirmation email for project requests

Date: 2026-08-24

## Finding

- Active employee template: `#20`, recipient `sales@solargy.group`, with configured BCC recipients.
- Active client template: `#32`, subject `Заявка принята — Solargy Казахстан`, recipient `#ATT_EMAIL#`.
- The custom handler explicitly passed message template `#20` to `CEvent::Send`, so template `#32` was never invoked.

## Backup

- Original handler: `backups/2026-08-24-client-confirmation-email/local-ajax-add_project_form.php.before`
- Backup commit: `03ccf77`

## Change

- Preserved the existing explicit send of template `#20` to employees with attached files.
- Added a second explicit send of template `#32` to the client after validating the submitted email address.
- Client confirmation is sent without customer-uploaded attachments.

## Verification

- The updated handler loads without a PHP fatal error and returns valid JSON on a read-only GET syntax check.
- A subsequent test request confirmed successful end-to-end delivery to the client mailbox.
- Confirmed sender: `sales@solargy.kz`.
- Confirmed subject: `Заявка принята — Solargy Казахстан`.
- Confirmed the HTML message contains the personalized greeting, submitted contact data, request summary, next steps, and contact buttons.

## Rollback

Restore `local-ajax-add_project_form.php.before` to `/local/ajax/add_project_form.php`.
