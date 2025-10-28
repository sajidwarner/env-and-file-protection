# 🔒 Laravel / PHP .htaccess Security Configuration

This repository includes a secure `.htaccess` configuration that helps protect your Laravel or PHP project from unauthorized access to sensitive files and directories.

## 🚀 Features

✅ Prevents access to critical files such as:
- `.env` (environment configuration)
- `.git` and version control files
- `.json`, `.lock`, `.config.js`
- `artisan` (Laravel CLI)
- `.md` and example files

✅ Disables directory browsing (prevents file listing)  
✅ Increases overall web application security  

---

## ⚙️ Installation

1. Copy the provided `.htaccess` code.
2. Paste it into your project’s root folder (where your `index.php` or `public/` folder exists).
3. Make sure Apache’s `mod_rewrite` and `.htaccess` overrides are enabled.

---

## 🧩 Code Example

```apache
# Prevent directory listing
Options -Indexes

# Restrict access to sensitive files
<Files ~ "\.(git|env|json|config.js|md|gitignore|gitattributes|lock|example)$">
    Order allow,deny
    Deny from all
</Files>

# Restrict access to Laravel artisan command file
<Files ~ "(artisan)$">
    Order allow,deny
    Deny from all
</Files>
