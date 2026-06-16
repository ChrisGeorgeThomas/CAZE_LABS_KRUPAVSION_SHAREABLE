# KRUPAVISION WordPress Backup Instructions

This backup consists of two parts:
1. **wordpress_files_backup.zip**: The entire WordPress file system (including themes, plugins, and uploads).
2. **wordpress_backup.sql**: The complete MySQL database export.

## Restoration Steps

1. **Files**: 
   - Rejoin the split zip parts (e.g., using PowerShell: `Get-Content wordpress_files_backup.zip.part* -Encoding Byte | Set-Content wordpress_files_backup.zip`).
   - Extract the contents of `wordpress_files_backup.zip` to your new web root.
2. **Database**: 
   - Create a new database in your hosted environment (e.g., using phpMyAdmin or MySQL CLI).
   - Import `wordpress_backup.sql` into that database.
3. **Configuration**:
   - Open `wp-config.php` in the extracted files.
   - Update the `DB_NAME`, `DB_USER`, `DB_PASSWORD`, and `DB_HOST` to match your new environment.
4. **Login**: 
   - The login URL is hidden for security. Use: `http://your-domain.com/caze-admin`
   - Use your existing WordPress credentials to log in.
   - If the domain has changed, you may need to update the `siteurl` and `home` options in the `wp_options` table.
