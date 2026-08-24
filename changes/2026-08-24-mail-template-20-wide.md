# Wider KEO request email

Date: 2026-08-24

## Scope

- Bitrix mail template `#20` used by the KEO/project request form.

## Backup

- Original template: `backups/2026-08-24-mail-template-20-wide/message-20.before.html`
- Backup commit: `ce43e8b`

## Change

- Increased the desktop email container from `620px` to a maximum of `800px`.
- Set the inline container width to `100%` with `max-width:800px` for responsive behavior on narrow screens.
- Kept the outer background and small side gutters for readability and email-client compatibility.

## Verification

- Reopened template `#20` after saving.
- Confirmed the new `width="800"` and `max-width:800px` markup is present.
- Confirmed the previous `620px` container markup is absent.
- No additional test email was sent for this presentation-only change.

## Rollback

Restore `message-20.before.html` into the `MESSAGE` field of Bitrix mail template `#20`.
