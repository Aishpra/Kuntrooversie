# Kuntroversie full private migration backup

Prepared 29 October 2026 from `C:/xampp/htdocs/kuntroversie`.
Source URL: `http://localhost/kuntroversie`.

## Contents and privacy

- `site/`: the complete installed WordPress files, including hidden `.htaccess`,
  WordPress core, all installed plugins/themes, uploads, and original wp-config.php.
- `database.sql`: all 53 tables of the local `kuntroversie_wp` database, including
  Elementor documents, revisions, menus, Blocksy settings, WooCommerce products,
  variations, orders, users and private site-inbox metadata.
- `database-verification.json`: an isolated database restore comparison.
- `file-manifest.json`: file sizes and SHA-256 hashes.
- Beside the ZIP: `BACKUP-VERIFICATION.json` and `SHA256SUMS.txt`.

This is a private, unencrypted backup, NOT a WordPress plugin installer. It
contains database credentials, authentication/encryption keys, account password
hashes, payment settings, saved submissions and logs. Keep it on trusted storage;
share only through your hosting provider's secure migration channel. Do not put
the ZIP, SQL, verification files or these instructions in a public web directory.
The database contains sandbox QA orders; these are not real sales or fulfilment.

## Restore onto hosting

1. Use an empty, access-restricted staging destination first. Back up any existing
   destination site before replacing anything. Provision PHP/MySQL compatible with
   this WordPress/plugin stack. PHP needs MySQLi, OpenSSL, Fileinfo and normal
   WordPress extensions; allow at least 5M upload_max_filesize and 20M post_max_size
   for the private Kustom attachments. Confirm the host's disk and archive limits.
2. Extract the archive OUTSIDE the public web root. Check SHA256SUMS.txt. Upload
   only the CONTENTS of `site/` to the intended WordPress document root, including
   hidden files and all wp-content uploads/plugins/themes. Retain the original
   wp-config.php privately and configure the destination before allowing access.
   Archived debug/payment logs need not be published on the destination.
3. Create a new hosting database and database user. Import `database.sql` into
   that EMPTY database with phpMyAdmin or the host's migration tool. The export
   does not create/switch database names. Keep the original `wp_` table prefix
   unless your migration tool deliberately changes all matching references.
4. Adapt wp-config.php to the host's DB_NAME, DB_USER, DB_PASSWORD and DB_HOST.
   Preserve the backed-up authentication keys/salts needed by the private Kustom
   attachment encryption. Do not regenerate AUTH_KEY/AUTH_SALT without first
   exporting/decrypting and safely re-encrypting the attachments. Do not blindly
   keep local debug, filesystem, absolute-path or other XAMPP-only settings.
   Set WP_DEBUG_DISPLAY false and use appropriate production logging.
5. Replace the old site URL with the actual HTTPS URL using a serialized-data-aware
   WordPress migration tool. Do not use a raw SQL text REPLACE on serialized data.
   With WP-CLI, run the following FROM THE DESTINATION install only, after taking
   a destination backup. Replace the example URL with your real URL:

   ```sh
   wp search-replace 'http://localhost/kuntroversie' 'https://your-domain.example' --all-tables-with-prefix --skip-columns=guid --precise --dry-run
   # Review the dry-run, then apply:
   wp search-replace 'http://localhost/kuntroversie' 'https://your-domain.example' --all-tables-with-prefix --skip-columns=guid --precise
   wp option update home 'https://your-domain.example'
   wp option update siteurl 'https://your-domain.example'
   ```

   Also inspect for any saved `127.0.0.1`/old localhost media URLs. Use Elementor's
   Replace URL tool for Elementor references, then regenerate CSS/data. Keep the
   local source and this original backup unchanged.
6. Save WordPress permalinks to regenerate rewrite rules for the destination path;
   the archived `.htaccess` is for `/kuntroversie/` on local Apache. Nginx/IIS hosts
   need their own rewrite configuration. Clear caches and test HTTPS media links,
   navigation, page layouts/animations and the Elementor editor save/reopen flow.
7. Test WooCommerce product/size/price data, guest/account checkout, both sandbox
   payments/refunds and signed webhook delivery on the actual HTTPS host. Connect
   real eligible merchant accounts only when ready; the archived PayPal merchant
   is a temporary US sandbox fixture and Stripe remains in test mode.
8. Configure the actual business address, shipping countries/rates, tax/stock rules,
   support mailboxes and authenticated email delivery. Local order email delivery
   was failing and no shipping methods/business address were configured. Verify
   order/refund/password-reset/form emails at real recipient inboxes.
9. Review policies/business claims and store visibility/indexing. Set a strong
   production administrator password directly in WordPress; local users/password
   hashes are preserved by this backup. Review sandbox QA records and payment
   sessions before launch. Keep recovery copies private after migration.

## What verification establishes

The SQL export is restored to an isolated temporary local database and every
table's row count and binary-safe content digest is compared with the source.
The temporary database is then removed. Every archived file is decompressed and
its SHA-256 checked. This proves archive/data integrity, not compatibility with an
unknown hosting environment. A full browser test on the destination remains
required; no hosting upload or live-payment activation has been performed.

References:
- https://developer.wordpress.org/advanced-administration/upgrade/migrating/
- https://developer.wordpress.org/cli/commands/search-replace/
