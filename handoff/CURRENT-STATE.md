# Current project state

## Backup to use

- Four files: `kuntroversie-complete.part1.rar` through `.part4.rar`, all in the repository root.
- Open part 1 with a RAR5-compatible extractor and the separately supplied password. Keep all parts together.
- Result: `kuntroversie-full-site-private.zip`.
- Inner ZIP SHA-256: `14C8F266580C24B30A29E208FE64DB4D5748C817991C68519D4907E3C77A1BB7`.
- 369,658,472-byte inner ZIP; 15,886 installed site files, 243 upload files, 53 database tables, 51 Elementor documents including preserved history.
- Inner ZIP contains `site/`, `database.sql`, database verification, manifest and restore instructions.
- The database was independently restored and compared; all ZIP payloads were decompressed and hash checked before upload. This is backup integrity proof, not a full restored-browser certification.

## Source-machine paths (historical Windows paths)

- Installed app: `C:/xampp/htdocs/kuntroversie`.
- Source workspace: `C:/Users/USER/Documents/ChatGPT/kuntroversie`.
- Plugin source: `wordpress-source/blocksy-plugin/`.
- Generated plugin: `wordpress-blocksy-package/kuntroversie-site/`.
- Child theme: `wordpress-blocksy-package/kuntroversie-blocksy-child/`.
- Installed plugin/theme and public media are fully captured inside the encrypted backup. The repository root itself contains backup volumes and documentation rather than extracted WordPress source.

## Files changed in latest premium pass

Relative to `site/wp-content/plugins/kuntroversie-site/` after extraction:

- `includes/native-catalogue.php` — Woo product rendering, description display, size prompt and assistance links.
- `includes/elementor/widget-product.php` — genuine editable controls.
- `includes/elementor/components.php` — editable film collection link.
- `assets/css/native-catalogue.css` — product/shop type and responsive controls.
- `assets/css/native-widgets.css` — collection link and previously fixed envelope geometry.
- `assets/css/blocksy-shell.css` — shared footer readability/controls.
- Generated `.full-motion.css` siblings of those styles must stay synchronized. The source Windows build generated them; they are already in this snapshot.

## Launch settings requiring owner input / fresh verification

At the last inspection: Stripe remained test-mode, PayPal sandbox connected, no enabled shipping methods, taxes disabled, store street address not configured, Kuntroversie form notifications disabled, local site HTTP. Previous SMTP/order email errors were recorded. These are historical snapshot findings; recheck them after restoring before proposing changes.

The owner has deferred merchant/hosting details. Do not invent shipping rates, tax obligations, care instructions, production promises, model measurements or live merchant credentials. Sandbox QA orders are not actual fulfilment requests.

## Restore essentials

Use an empty destination database and the backed-up `wp_` prefix. Set new destination DB connection details. Preserve authentication/encryption salts needed by private Kustom attachments. Use serialized-aware URL replacement, regenerate Elementor CSS and permalinks, and account for Linux filesystem case sensitivity and Apache/Nginx rewrite rules. Keep SQL, archives, logs and private documents outside public directories. See the root restore guide for the detailed procedure.
