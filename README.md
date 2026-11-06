# NextDNS Manager

An iOS Shortcut for managing and checking your NextDNS profile without needing to visit the NextDNS website or app. Includes sideloading features such as auto-setup of the famous sideloading ruleset, and easy PPQ block toggling. 

The shortcut only uses native Shortcuts actions, no external app actions needed!  
Should be compatible with iOS 18+, though so far only tested on iOS 26.

## Previews

<table align="center">
  <tr>
    <th width="50%">Main Menu</th>
    <th width="50%">Config Menu</th>
  </tr>
  <tr>
    <td align="center" valign="top">
      <img src="https://github.com/user-attachments/assets/5934dfc1-9113-468b-beee-786416c3a862" alt="Main Menu" height="380">
    </td>
    <td align="center" valign="top">
      <img src="https://github.com/user-attachments/assets/83a35d7d-9bb2-40bc-8601-377afbee8af2" alt="Config Menu" height="380">
    </td>
  </tr>
</table>

<table align="center">
  <tr>
    <th width="33%">Check Status</th>
    <th width="34%">Analytics Status</th>
    <th width="33%">Sideloading Status</th>
  </tr>
  <tr>
    <td align="center" valign="top">
      <img src="https://github.com/user-attachments/assets/30627eaf-855a-424a-8531-0e1cf9a615b6" alt="Check Status" height="270">
    </td>
    <td align="center" valign="top">
      <img src="https://github.com/user-attachments/assets/4d11afc8-e808-41ce-9d92-819f98d8a05e" alt="Analytics Status" height="270">
    </td>
    <td align="center" valign="top">
      <img src="https://github.com/user-attachments/assets/0adb6020-a8db-4caa-a7f7-65173ad91a3b" alt="Sideloading Status" height="270">
    </td>
  </tr>
</table>


## Features

- **Check Status**   
  View your NextDNS profile's denylist, allowlist, privacy blocklists, security protections, and analytics
- **PPQ Blocking**  
  Easily enable or disable PPQ domain blocking for sideloading apps
- **Sideloading Ruleset**   
  Auto-setup the famous DNS blocking ruleset for sideloading iOS apps, or remove it
- **Custom DNS Rules**   
  Add or remove any domains from your denylist and allowlist
- **Network Refresh**   
  Automatically refreshes wifi and cellular connections after any DNS changes
- **Quick Access**   
  Open the NextDNS website, app, or your device's DNS settings directly from the shortcut
- **Change Preferences**   
  Your settings will be saved to the  `config.json` which is created in the Files app at `iCloud Drive\Shortcuts\NextDNS Manager\config.json` 
  - Network refresh wait time interval   
  - What to re-enable after network refresh (wifi only or wifi + cellular)  
  - Show or hide sideloading features  
  - Show or skip success confirmation popups after actions complete  
  - Add an extra 'Open NextDNS App' option to main menu  

## Setup

1. [Download the shortcut](https://www.icloud.com/shortcuts/5d8cf8074454426ea226fbd5cca22551) directly with iCloud, the `.shortcut` is also provided in this repo
2. Open the shortcut's actions in the Apple Shortcuts app
3. In the first two text fields, replace `PASTE_API_KEY_HERE` and `PASTE_PROFILE_ID_HERE` with your NextDNS API key and Profile ID
   - Copy your API key from the [NextDNS website](https://my.nextdns.io/), when signed in go to Account page and scroll down. 
   - Copy profile ID can be found in the 'Setup' tab under 'Endpoints' 
4. Run the shortcut

**Disclaimer**  
Do not share your install of the shortcut once setup, others will end up receiving it with your API key included.

## Sideloading Info

### Sideloading Denylist Ruleset

The auto-setup for sideloading feature will add & enable these denylist rules:
- `ppq.apple.com`
- `ocsp2.apple.com`
- `vpp.itunes.apple.com`
- `valid.apple.com`
- `ocsp.apple.com`
- `crl.apple.com`
- `certs.apple.com`
- `appattest.apple.com`
    
When installing sideloaded apps, make sure to toggle off PPQ/`ppq.apple.com`, once you're done sideloading apps, toggle it back on. Simple as that. 

#### If you use ChatGPT on your device & are having issues

People recommend to add these domains to your NextDNS allowlist, if you're having trouble with ChatGPT such as logging in/verification and such. 

> Dev note:
> Personally, I've never experienced any issues or need to add these. I would say only add them if you are having problems. Start with the first one, if you're still having issues, add the second as well. 

- `register.appattest.apple.com`
- `app.localhost.direct` 

## For developers

The shortcut was developed using [Cherri](https://github.com/electrikmilk/cherri). The [`dev/`](dev/) directory contains the build script.
