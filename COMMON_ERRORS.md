# Common Errors and Solutions

### "Failed to initialize Steam Platform"

Make sure Steam is running in the background and that you are logged into your account.

> [!note]
> Your Steam profile must be set to **Public**, and **Rec Room** must be present in your Steam library.

### "Rec Room update required"

This error usually occurs when `BepInEx\plugins\Radeon.Core.BasePatch.dll` has been removed, often by Windows Defender or another antivirus program.

To fix this:

1. Read the [README](README.md#section-4-adding-windows-defender-exclusions) in order to disable Windows Defender (and add an exclusion)
2. Open the original Radium `.zip` file.
3. Navigate to `BepInEx\plugins`.
4. Copy `Radeon.Core.BasePatch.dll`.
5. Open your Radium installation folder and navigate to `BepInEx\plugins`.
6. Paste the file into the folder.

After restoring the file, launch the application again.

### "Login failed, please try again"
This error usually occurs when the servers are undergoing maintenance or experiencing temporary issues.<br>
If this happens, wait a few minutes and try again later. If the problem persists, check for announcements regarding server status or maintenance.
