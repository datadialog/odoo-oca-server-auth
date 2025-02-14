To enable this feature, once the module installed, you have to add the
following keys in your `odoo.cfg` configuration file.

- `auth_admin_passkey_password`. The password that allows user to
  logging in with any login. If not set, the feature is disabled.
- `auth_admin_passkey_password_sha512_encrypted` (default False), if
  enabled, auth_admin_passkey_password should be the password encrypted
  with sha512. On linux, this can be done using this command:
  `echo -n YOUR_PASSWORD_AUTH_ADMIN_PASSKEY | sha512sum`
- `auth_admin_passkey_send_to_user` (default True), if enabled, an email
  will be send to the user, if his account has been used by the System
  Administrator.
- `auth_admin_passkey_sysadmin_email`. If set, an email will be sent to
  this mail.
- `auth_admin_passkey_sysadmin_lang`. the language (exemple en_US), used
  for the mail sent to the System Administrator. If not set, the
  language of the SUPERUSER_ID user will be used.
- `auth_admin_passkey_ignore_totp` (default False), if enabled, then 2FA
  will be ignored.

**typical Dev / Test configuration section**

No keys to add.

**typical Production configuration section**

``` ini
auth_admin_passkey_password = PASSKEY_PASSWORD
auth_admin_passkey_password_sha512_encrypted = True
auth_admin_passkey_send_to_user = True
auth_admin_passkey_sysadmin_email = SYSADMIN_EMAIL
auth_admin_passkey_sysadmin_lang = SYSADMIN_LANG
```
