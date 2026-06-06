# Installing and Playing Radium

This guide will walk you through downloading Radium, creating an account, linking Discord, configuring Windows Defender, and launching the game.

---

# Section 1: Downloading Radium

To download Radium, first join the Radium Discord server.

Once you've joined, navigate to the `#💾｜download` channel and download the appropriate version:

* `.ipa` files are for iOS devices.
* `.zip` and `.dll` files are for Windows.

## Oculus / Quest Installation

### Verify Your Meta Account

In `#🤖｜bot-commands`, run the `/verify-oculus` command using the username or email address associated with your Meta account.

> [!note]
> Meta usernames are case-sensitive. Enter your username exactly as it appears on your account.

#### Example

If your username is `CoolBoy2011`, enter:

`CoolBoy2011`

Do not enter:

* `COOLBoy2011`
* `CoolBOY2011`
* Any other variation

### Accept the Invitation

Check your email for an invitation from *RecRoomArchive* and accept it.

### Install and Play

Put on your headset and open your Quest app library.

You should see **Radium** listed among your applications. If it does not appear immediately, restart your headset and check again.

> [!note]
> This is a temporary installation method while the Radium team awaits App Lab approval, which will simplify installation in the future.

---

# Section 2: Creating a Radium Account

Visit the Radium website and click **Sign Up**.

Enter the following information:

* Username
* Password
* Date of birth

### Example

![How it should look](image.png)

Once you've filled out the form, click **Create Account**.

### Account Created

Your Radium account is now ready to use.

---

# Section 3: Linking Your Discord Account

Before you can play, you must link your Discord account to your Radium account.

## Getting a Verification Code

Navigate to `#🤖｜bot-commands` and run the `/link` command.

Make sure you're using the Radium bot's slash command rather than simply typing `/link` as a message.

The bot will provide a verification code.

> [!warning]
> Never share your verification code with anyone.

> [!note]
> If the Radium bot does not respond, it may be temporarily offline. Please wait and try again later.

## Using the Verification Code

Open the Radium Settings page and locate the **Link Discord** section.

Enter your verification code.

![Example](image-1.png)

Click **Verify and Link**.

If the link was successful, you should see your Discord account information displayed.

![Verified Discord User Info](image-2.png)

If no Discord user information appears, try linking again or contact Radium support.

---

# Section 4: Adding Windows Defender Exclusions

> [!note]
> If you are not using Windows, you can skip this section.

## Before You Begin

Extract the Radium ZIP file before continuing.

### Disable Real-Time Protection and Tamper Protection

1. Open **Windows Security**.
2. Navigate to **Virus & threat protection**.
3. Under **Virus & threat protection settings**, click **Manage settings**.
4. Temporarily disable:

   * Real-time protection
   * Tamper Protection
5. Accept any User Account Control (UAC) prompts.

### Using PowerShell

Check the current Defender status:

```pwsh
Get-MpComputerStatus
```

Review the `IsTamperProtected` field.

If it is set to `True`, disable Tamper Protection through Windows Security, as PowerShell cannot disable it.

Disable real-time monitoring:

```pwsh
Set-MpPreference -DisableRealtimeMonitoring $true
```

Re-enable it afterward:

```pwsh
Set-MpPreference -DisableRealtimeMonitoring $false
```

## Adding an Exclusion

1. Open **Windows Security**.
2. Navigate to **Virus & threat protection**.
3. Under **Virus & threat protection settings**, select **Manage settings**.
4. Scroll to **Exclusions**.
5. Click **Add or remove exclusions**.
6. Select **Add an exclusion** → **Folder**.
7. Choose your Radium installation folder.

### Using PowerShell

```pwsh
Add-MpPreference -ExclusionPath "C:\path\to\your\radium\folder"
```

Replace the example path with the location of your Radium installation.

> [!important]
> Re-enable Real-time Protection and Tamper Protection after adding the exclusion.

---

# Section 5: Launching Radium

You are now ready to launch the game.

Open your Radium installation folder. You should see the following batch files:

* `RecRoom_ScreenMode.bat` — Launches the game in desktop mode.
* `RecRoom_VR.bat` — Launches the game in VR mode.
* `RecRoomLog.bat` — Opens the game's log directory and does not launch the game.

## Signing In

Once Rec Room starts, select:

**Sign in to an existing Rec Room account**

Use the Radium account you created earlier.

Enter your:

* Username
* Password

Optionally enable **Remember Password**, then click **Sign In**.

---

# Congratulations

You have successfully installed and configured Radium.

If you encounter any issues, visit the `#❓｜help` channel and describe the problem you're experiencing.

You can also review the [**Common Errors**](COMMON_ERRORS.md) guide for solutions to frequently reported issues.
