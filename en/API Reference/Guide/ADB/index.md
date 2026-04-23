# ADB Connection Guide

This guide provides detailed instructions for connecting to cloud phone devices via ADB, supporting **Android 12/15** and **Android 13/14** versions.

---

## 1. ADB Connection for Android 12 / Android 15 Cloud Phones

### Step 1: Connect to the Cloud Phone IP and Port

Use the `adb connect` command to directly connect to the cloud phone's IP address and port.

```bash
adb connect 172.168.10.1:123456
```

> Replace `172.168.10.1:123456` with your actual cloud phone IP and port.

### Step 2: Authenticate with Connection Code

After successful connection, authenticate using the connection code.

```bash
adb shell 123456
```
After successful authentication, you will be defaulted to enter the cloud phone, and you can use "exit" to log out
```bash
exit
```

Or specify the device address:

```bash
adb -s 172.168.10.1:123456 shell 123456
```

> Note: The connection code is usually provided by the cloud phone platform. Ensure it is entered correctly.

---

## 2. ADB Connection for Android 13 / Android 14 / Android 15A / Android 16 Cloud Phones

For these versions, an SSH tunnel must be established to forward the ADB port. This requires two steps.

### Step 1: Establish SSH Tunnel (Open First CMD Window)

Run the following SSH command to map the remote ADB port to your local machine:

```bash
ssh -oHostKeyAlgorithms=+ssh-rsa 10.2.179.250_1763627294587@107.151.131.2 -p 1824 -L 9897:adb-proxy:14566 -Nf
```

> Notes:
> - Replace the username, IP, and port in the command with your actual configuration.
> - When prompted for a password, paste the SSH password and press Enter.
> - The command will not produce any output if successful, indicating the tunnel is running in the background.

### Step 2: Connect to Local ADB Port (Open Second CMD Window)

In a new window, execute the ADB connection command:

```bash
adb connect localhost:9897
```

Successful output example:

```
connected to localhost:9897
```

---

## Complete Workflow Example

### 1. First CMD Window (SSH Tunnel):

```bash
ssh -oHostKeyAlgorithms=+ssh-rsa 10.2.179.250_1763627294587@107.151.131.2 -p 1824 -L 9897:adb-proxy:14566 -Nf
```
Next, enter the SSH connection password

### 2. Second CMD Window (ADB Connection):

```bash
adb connect localhost:9897
```

---

## Verify Connection Status

Run the following command to check if the device is connected:

```bash
adb devices
```

Expected output:

```
List of devices attached
localhost:9897     Device
```

---

## Common ADB Commands Reference

| Command | Description |
|--------|-------------|
| `adb devices` | List connected devices |
| `adb shell` | Enter device shell terminal |
| `adb shell pm list packages` | List installed apps |
| `adb install app.apk` | Install APK file |
| `adb uninstall package.name` | Uninstall app |
| `adb reboot` | Reboot device |

---

## Important Notes

- Ensure you have installed [Android SDK Platform Tools](https://developer.android.com/studio/releases/platform-tools) and configured environment variables.
- The SSH tunnel method for Android 13/14/15A is encrypted and secure — recommended for use.
- If connection times out, check network settings, firewall rules, and port configurations.
- Always confirm that the cloud phone is powered on and ADB access is enabled before connecting.

---

Follow these steps to successfully connect your cloud phone for ADB debugging and automation tasks.