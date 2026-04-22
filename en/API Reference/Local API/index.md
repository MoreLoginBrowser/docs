# MoreLogin Local API Usage Guide

The MoreLogin local API allows you to programmatically manage anti-detection browser profiles and cloud phones directly from your own machine. This guide explains what you can do, how to access the API, and key usage notes.

---

## API Endpoint

The API runs locally on your computer and is accessible at:

```
http://127.0.0.1:40000
```

All requests must be sent to this base URL.  
Example:
```bash
POST http://127.0.0.1:40000/api/env/create/quick
```

> **Security Note**:  
> The API is only available on `localhost` for security. It cannot be accessed remotely. 
> Morelogin also provides an open API. Please refer to the documentation for more information[MoreLogin Open API Documentation](https://guide.morelogin.com/api-reference/open-api/open-api)

---

## Browser Profile Management

### Create Browser Profiles
Create one or multiple anti-detection browser profiles instantly.

- **Quick Create**: `POST /api/env/create/quick`
  - Specify OS: Windows, macOS, Android, iOS
  - Choose browser: Chrome or Firefox
  - Set optional password encryption
  - Batch create up to 50 profiles in one request

- **Advanced Create**: `POST /api/env/create/advanced`
  - Full customization of fingerprint settings (User-Agent, time zone, language, resolution, fonts, WebGL, etc.)
  - Configure proxy, group, tags, and account info
  - Set advanced security features (audio/video/image blocking, extensions, etc.)

### Refresh Fingerprint
Regenerate device fingerprint (User-Agent, screen size, fonts, WebGL, etc.) to simulate a new device.

- **Endpoint**: `POST /api/env/fingerprint/refresh`
- **Options**: Define target browser version (e.g., Chrome 129), OS, and browser type

###  Close a Running Profile
Terminate an active browser instance.

- **Endpoint**: `POST /api/env/close`
- **Required**: Provide `envId` or `uniqueId` of the profile

### Start a Browser Profile
Launch a browser profile and get its debug interface for automation.

- **Endpoint**: `POST /api/env/start`
- **Required**: Provide `envId` or `uniqueId` of the profile
- **Returns**: Debug port, WebDriver path, and connection details for Selenium/Puppeteer

### Check Profile Status
Get real-time status, debug port, and WebDriver info.

- **Endpoint**: `POST /api/env/status`
- **Returns**: Whether the profile is running, its remote debugging URL, and process details

### Get Profile List
Retrieve a list of browser profiles with filtering options.

- **Endpoint**: `POST /api/env/page`
- **Filters**: By name, group ID, or specific environment ID

### Get Profile Details
Retrieve detailed configuration of a specific browser profile.

- **Endpoint**: `POST /api/env/detail`
- **Required**: `envId` of the profile

### Clear Profile Cache
Remove local cache data (cookies, localStorage, IndexedDB, etc.) without affecting the profile config.

- **Endpoint**: `POST /api/env/removeLocalCache`
- **Options**: Select which cache types to clear

### Delete Browser Profile
Move browser profiles to the recycle bin.

- **Endpoint**: `POST /api/env/removeToRecycleBin/batch`
- **Required**: List of `envIds` to delete

---

## Cloud Phone Management

### Create a New Cloud Phone
Provision a virtual Android device.

- **Endpoint**: `POST /api/cloudphone/create`
- **Options**: Choose Android version (12-15A), set location, language, timezone, proxy, and other settings

### Shut Down Cloud Phone
Stop a running cloud phone instance.

- **Endpoint**: `POST /api/cloudphone/powerOff`
- **Required**: Cloud phone ID

### Start Cloud Phone
Start a cloud phone instance.

- **Endpoint**: `POST /api/cloudphone/powerOn`
- **Required**: Cloud phone ID

###Get Cloud Phone List
Retrieve a list of cloud phones with filtering options.

- **Endpoint**: `POST /api/cloudphone/page`
- **Filters**: By keyword (proxy info, group, tag, name), IP binding status, etc.

### Get Cloud Phone Details
Retrieve full configuration of a cloud phone, including:

- ADB connection info (IP, port, password)
- Proxy status
- Assigned group and tags
- Location & sensor settings

- **Endpoint**: `POST /api/cloudphone/info`
- **Required**: `id` of the cloud phone

### Modify Cloud Phone
Update cloud phone settings (location, language, timezone, proxy, group, tags).

- **Endpoint**: `POST /api/cloudphone/edit/batch`
- **Required**: List of cloud phone IDs to update

### Delete Cloud Phone
Remove cloud phone profiles.

- **Endpoint**: `POST /api/cloudphone/delete/batch`
- **Required**: List of cloud phone IDs to delete

### One-click New Cloud Phone
Reset a cloud phone to a fresh state.

- **Endpoint**: `POST /api/cloudphone/newMachine`
- **Required**: Cloud phone ID

### Update ADB Status
Enable or disable ADB access for cloud phones.

- **Endpoint**: `POST /api/cloudphone/updateAdb`
- **Required**: List of cloud phone IDs and enable/disable flag

### Execute Shell Command
Run shell commands on cloud phones via ADB.

- **Endpoint**: `POST /api/cloudphone/exeCommand`
- **Required**: Cloud phone ID and command string

---

## Cloud Phone File Management

### Upload Files
Upload files to cloud phone storage.

- **Endpoint**: `POST /api/cloudphone/uploadFile`
- **Required**: File, cloud phone ID, and destination directory

### Upload Status
Check the status of a file upload.

- **Endpoint**: `POST /api/cloudphone/uploadUrl`
- **Required**: Cloud phone ID and file ID

### Set Keybox
Configure keybox settings for cloud phones.

- **Endpoint**: `POST /api/cloudphone/setKeyBox`
- **Required**: File path and cloud phone ID

---

## Cloud Phone App Management

### Install App
Install an app on a cloud phone.

- **Endpoint**: `POST /api/cloudphone/app/install`
- **Required**: Cloud phone ID and app version ID or package name

### Get App List
Retrieve a list of available apps.

- **Endpoint**: `POST /api/cloudphone/app/page`
- **Filters**: By app name, pagination

### Get Installed Apps
List apps installed on a specific cloud phone.

- **Endpoint**: `POST /api/cloudphone/app/installedList`
- **Required**: Cloud phone ID

### Launch App
Start an installed app on a cloud phone.

- **Endpoint**: `POST /api/cloudphone/app/start`
- **Required**: Cloud phone ID and package name

### Restart App
Restart an installed app on a cloud phone.

- **Endpoint**: `POST /api/cloudphone/app/restart`
- **Required**: Cloud phone ID and package name

### Stop App
Stop an installed app on a cloud phone.

- **Endpoint**: `POST /api/cloudphone/app/stop`
- **Required**: Cloud phone ID and package name

### Uninstall App
Remove an app from a cloud phone.

- **Endpoint**: `POST /api/cloudphone/app/uninstall`
- **Required**: Cloud phone ID and package name

---

## Proxy Management

### Get Proxy List
Retrieve a list of configured proxies with filtering options.

- **Endpoint**: `POST /api/proxyInfo/page`
- **Filters**: By IP, name, status, type, provider, etc.

### Add Proxy
Add a new proxy configuration.

- **Endpoint**: `POST /api/proxyInfo/add`
- **Required**: Proxy IP, port, type, and optional authentication

### Update Proxy
Modify an existing proxy configuration.

- **Endpoint**: `POST /api/proxyInfo/update`
- **Required**: Proxy ID and updated parameters

### Delete Proxy
Remove proxy configurations.

- **Endpoint**: `POST /api/proxyInfo/delete`
- **Required**: List of proxy IDs to delete

---

## Group Management

### Get Group List
Retrieve a list of environment groups.

- **Endpoint**: `POST /api/envgroup/page`
- **Filters**: By group name, pagination

### Create Group
Add a new environment group.

- **Endpoint**: `POST /api/envgroup/create`
- **Required**: Group name

### Edit Group
Update an existing group's name.

- **Endpoint**: `POST /api/envgroup/edit`
- **Required**: Group ID and new name

### Delete Group
Remove an environment group.

- **Endpoint**: `POST /api/envgroup/delete`
- **Required**: Group ID(s) and deletion options

---

## Tag Management

### Get Tag List
Retrieve all available tags.

- **Endpoint**: `GET /api/envtag/all`

### Create Tag
Add a new tag.

- **Endpoint**: `POST /api/envtag/create`
- **Required**: Tag name

### Edit Tag
Update an existing tag's name.

- **Endpoint**: `POST /api/envtag/edit`
- **Required**: Tag ID and new name

### Delete Tag
Remove tags.

- **Endpoint**: `POST /api/envtag/delete`
- **Required**: List of tag IDs to delete

---

## Getting Started Example

Create a Chrome profile on Windows:

```bash
curl -X POST "http://127.0.0.1:40000/api/env/create/quick" \
  -H "Content-Type: application/json" \
  -d '{
    "browserTypeId": 1,
    "operatorSystemId": 1,
    "quantity": 1
  }'
```

Response includes `envId`, which you can use to start, close, or check status later.

---

## Requirements

- MoreLogin desktop app installed and running (v2.15.0 or later recommended)
- Request must be made by logging into the morelogin account
- Requests must originate from the same machine (no remote access)

---

> **Tip**: Use this API to build custom automation tools, integrate with RPA platforms, or orchestrate multi-account workflows—all while maintaining session isolation and fingerprint integrity.

For detailed request/response schemas, refer to the official API documentation at [MoreLogin Local API Documentation](https://guide.morelogin.com/api-reference/local-api/local-api).