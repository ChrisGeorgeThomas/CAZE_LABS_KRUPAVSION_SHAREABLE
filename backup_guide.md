# Project Backup & Sharing Guide: KRUPAVISION

To share the entire project with someone else, you need to provide two main components:
1. **The Database** (all your posts, pages, and settings).
2. **The Files** (the WordPress core, themes, and plugins).

---

## Method 1: The "Best" way (Using a Plugin)
This is the most reliable method because it packages everything into a single file and provides an automated installer for the recipient.

1. **Install "Duplicator"**: Log in to your WordPress dashboard and install the [Duplicator](https://wordpress.org/plugins/duplicator/) plugin.
2. **Create a Package**:
   - Go to **Duplicator > Packages** and click **Create New**.
   - Follow the wizard (Scan -> Build).
3. **Download**: Once finished, download both the **Archive** (a `.zip` file) and the **Installer** (an `installer.php` file).
4. **Share**: Send these two files to the other person. They will just need to upload them to their server and run `installer.php`.

---

## Method 2: Manual Export (Files + SQL)
If you prefer not to use a plugin, follow these steps:

### Step A: Export the Database
1. Open your database management tool (e.g., phpMyAdmin or the MySQL command line).
2. Select the `wordpress` database.
3. Click **Export** and save it as `wordpress_latest.sql`.
4. Move this file into your project root: `C:\KRUPAVISION_FINAL_DRAFT\`.

### Step B: Compress the Project Folder
1. Navigate to: `C:\`
2. Right-click the folder `KRUPAVISION_FINAL_DRAFT`.
3. Select **Compress to ZIP file** (Windows 11) or **Send to > Compressed (zipped) folder**.
4. This will create a file named `KRUPAVISION_FINAL_DRAFT.zip`.

### Step C: Share
1. Upload the `KRUPAVISION_FINAL_DRAFT.zip` to a cloud storage service (Google Drive, Dropbox, WeTransfer).
2. Share the link with the recipient.

---

## What the Recipient Needs to Do
1. Unzip the folder.
2. Follow the [Hosted Environment User Guide](file:///C:/KRUPAVISION_FINAL_DRAFT/user_guide.md) to set up the files and database on their machine.

> [!IMPORTANT]
> Make sure your database export is fresh before zipping the folder. The existing `wordpress.sql` in `CAZE_LABS` may be outdated.
