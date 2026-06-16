# KRUPAVISION: Hosted Environment User Guide

This guide provides instructions on how to deploy and manage the KRUPAVISION project in a hosted environment.

## Local Project Storage
The project files are currently stored on your local machine at:
`C:\KRUPAVISION_FINAL_DRAFT`

### Directory Structure Overview
- `\wordpress`: Contains the full WordPress core, themes, and plugins. This is the directory you will upload to your web server.
- `\CAZE_LABS`: Contains database backups and utility scripts.
    - `wordpress.sql`: The database export for the project.

---

## 1. Prerequisites
Ensure your hosting environment meets the following requirements:
- **PHP**: version 7.4 or higher (8.1+ recommended).
- **Database**: MySQL 5.7+ or MariaDB 10.3+.
- **Web Server**: Apache (with `mod_rewrite` enabled) or Nginx.

---

## 2. Step-by-Step Deployment

### Step A: Upload Project Files
1. Connect to your hosting server via FTP/SFTP (using tools like FileZilla) or use the File Manager in your hosting panel (e.g., cPanel).
2. Upload the contents of the `C:\KRUPAVISION_FINAL_DRAFT\wordpress` directory to your server's root directory (usually `public_html`, `www`, or `httpdocs`).

### Step B: Create and Import Database
1. Log in to your hosting control panel and create a new MySQL/MariaDB database.
2. Create a database user and assign them to the new database with "All Privileges".
3. Open **phpMyAdmin** from your control panel.
4. Select the new database, click the **Import** tab, and choose the file:
   `C:\KRUPAVISION_FINAL_DRAFT\CAZE_LABS\wordpress.sql`
5. Click **Go** to import the tables and data.

### Step C: Configure WordPress
1. On your server, find the `wp-config.php` file in the root directory.
2. Edit the file to match your new database credentials:
   ```php
   define( 'DB_NAME', 'your_database_name' );
   define( 'DB_USER', 'your_username' );
   define( 'DB_PASSWORD', 'your_password' );
   define( 'DB_HOST', 'localhost' ); // Or your host's DB server address
   ```
3. Save the changes.

### Step D: Update Site URLs (If domain changes)
If your hosted domain is different from your local development URL, you may need to update the site URLs in the database:
1. In phpMyAdmin, go to the `wp_options` table.
2. Find `siteurl` and `home` rows and update them to your new domain (e.g., `https://yourdomain.com`).
3. (Optional) Use a "Search and Replace" plugin (like "Better Search Replace") once logged in to update all internal links.

---

## 3. Troubleshooting
- **404 Errors on Subpages**: Ensure your `.htaccess` file was uploaded and that your server allows overrides.
- **Database Connection Error**: Double-check the credentials in `wp-config.php`.
- **White Screen of Death**: Check the error logs (`wp-content/debug.log`) if `WP_DEBUG` is enabled.

---

> [!TIP]
> Always keep a backup of your `wp-config.php` and `wordpress.sql` before making major changes in the hosted environment.
