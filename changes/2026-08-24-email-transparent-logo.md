# Transparent PNG logo in application emails

## Change

- Uploaded the owner-provided transparent PNG as `/local/templates/solargy/assets/img/logo-email.png`.
- Verified the public asset: `579 x 112` pixels.
- Updated mail template `20` (staff notification).
- Updated mail template `32` (client confirmation).
- Replaced `logo2.jpg` with `logo-email.png` and changed the rendered dimensions from `200 x 50` to proportional `200 x 39` pixels.

## Verification

- Reopened both templates after saving.
- Both templates contain `logo-email.png` and `width="200" height="39"`.
- Neither template contains the former `logo2.jpg` reference.
- No test form was submitted as part of this change.

## Rollback

Restore `https://solargy.kz/local/templates/solargy/assets/img/logo2.jpg` and dimensions `200 x 50` in templates `20` and `32`. The previous asset was not overwritten or deleted.
