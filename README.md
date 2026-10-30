# Kuntroversie — complete WordPress backup

This repository contains the **entire verified site backup**, including WordPress core, installed plugins and themes, the Blocksy child theme, Kuntroversie global plugin, Elementor edits, WooCommerce catalogue and database, and uploads.

Snapshot: **30 October 2026**, including the latest designer-brand refinements.

## Download and open

1. On GitHub, choose **Code → Download ZIP** and extract the downloaded repository ZIP.
2. Keep all four `kuntroversie-complete.part*.rar` files together in the same folder.
3. Open **`kuntroversie-complete.part1.rar`** with WinRAR or a compatible RAR5 extractor and enter the archive password supplied separately in the chat. The password is intentionally absent from this public repository.
4. Extract `kuntroversie-full-site-private.zip`, then extract that ZIP. It contains the complete `site/` folder, `database.sql`, file manifest and restore instructions.

The volume set was encrypted with RAR5 header encryption and tested successfully before upload. `SHA256-MANIFEST.json` lists the encrypted-volume hashes; `BACKUP-VERIFICATION.json` records the original ZIP hash and its database/file verification results.

## Restore to hosting

Read **RESTORE-INSTRUCTIONS.md** first. In brief:

- Upload the contents of `site/` into your hosting document root.
- Create an empty hosting database and import `database.sql`.
- Set the hosting database credentials in `wp-config.php`.
- Keep the original authentication salts when restoring this snapshot: private Kustom attachments depend on them.
- Replace `http://localhost/kuntroversie` with the final HTTPS URL using a WordPress-aware serialized-data replacement tool. Run a dry run first.
- Regenerate Elementor CSS and save WordPress permalinks.
- Recheck checkout, email, destination shipping, tax settings and payment webhooks on the hosting domain.

This is a complete snapshot, **not a declaration that the live shop is ready for paid orders**. Its payment accounts are sandbox/test accounts. Shipping, merchant business information, SMTP and live payment setup still need confirmation/configuration.

## Privacy

The encrypted archive includes private database/configuration information because it is a full migration backup. **Do not upload the decrypted archive, SQL, wp-config.php or archive password into this public repository.** On hosting, upload site contents only; keep the SQL, ZIP, RAR volumes and reports outside public web folders after restoration.

## Included verification

- 15,886 installed site files, including 243 uploads.
- 53 database tables and 51 Elementor documents (including preserved database history).
- All 15,889 backup payloads decompressed and checked against SHA-256 manifests.
- Database independently restored and compared; temporary verification database removed.
- Latest local design checks: 306 storefront checks, 73 component checks, 29 catalogue checks and upload-package verification.
