# Privacy Policy — Xenon Download Manager & Browser Extension

**Last updated:** 2026-11-23

Xenon Download Manager and the Xenon Download Manager browser extension do **not** collect, sell, share, or transmit your personal data to the developer or any third party. There are no accounts, no analytics, no telemetry, and no advertising.

Because Xenon Download Manager is open-source software ([github.com/gglemas/Xenon-Download-Manager](https://github.com/gglemas/Xenon-Download-Manager)), every network request and permission described below can be verified directly in the source code.

## Browser Extension

The Xenon Download Manager extension for Chrome, Edge, Brave, Opera, Vivaldi, and Firefox communicates **exclusively** with the locally installed Xenon Download Manager desktop application on your computer (via the browser's Native Messaging API) or, if you explicitly pair one, your own Xenon Download Manager instance on your local network.

### What the extension accesses locally
- **Downloads & links:** When you start a download that matches your configured file-type rules (or right-click a link/selection/page to download with Xenon), the extension passes the download URL, redirect chain, referring page URL, file name, size, MIME type, cookies for that specific URL, and your browser's `User-Agent` to your local Xenon Download Manager desktop app so downloads behind logins work reliably.
- **Form submissions:** For downloads triggered by an HTML form submission, the extension temporarily holds the form body in memory (never saved to disk, discarded within two minutes) so Xenon can repeat the download request locally.
- **Media & subtitle detection:** The extension observes active-tab media streams (HLS/DASH playlists, unencrypted audio/video, and VTT/SRT subtitle tracks) in memory per tab so the popup and on-page Download button can hand them to your local Xenon app. DRM-protected streams are detected passively and marked as protected rather than downloaded.
- **Optional proxy forwarding:** Disabled by default. Only if you explicitly turn on the popup's proxy switch does the extension read your browser's active proxy address or PAC script URL (never proxy credentials) so Xenon downloads through the same proxy or VPN.
- **Local settings (`storage`):** The extension stores your local preferences (capture pause toggle, synced file-type/exclusion rules from Xenon, proxy switch state, video button corner position per site, and interface language) locally in `chrome.storage`. Nothing from private/incognito windows is persisted.

### Why each permission is requested
- `downloads`: Intercepts browser downloads matching your rules and hands them off to Xenon Download Manager.
- `contextMenus`: Adds right-click actions to download individual links, selected links, or all links on a page.
- `nativeMessaging`: Communicates locally with `com.xdm.host` (the installed Xenon Download Manager desktop app).
- `cookies`: Passes session cookies for the specific URL being downloaded to your local Xenon app so authenticated downloads succeed.
- `storage`: Saves your extension settings locally in the browser.
- `webRequest`: Observes active-tab media streams, subtitles, redirects, and form-triggered downloads in memory (read-only).
- `scripting`: Displays the optional Download button over page videos and collects page/selected links when requested.
- `declarativeNetRequestWithHostAccess`: Uses temporary session rules when you enable capturing inline-opened file types (such as PDFs) instead of displaying them in the browser.
- `proxy`: Reads the browser's proxy configuration only when you turn on the optional proxy-forwarding switch in the popup.
- `Host permissions (<all_urls>)`: Downloads, links, and media can come from any website you visit; access is never used for tracking or advertising.

## Desktop Application

Your download list, settings, and downloaded files stay strictly on your own computer. Passwords saved in Sites Logins or account settings are stored in your operating system's credential manager. The desktop app connects only to the servers you download from (plus GitHub when you check for app updates or install optional `yt-dlp`/`ffmpeg` video helpers).

## Data Collection & Third-Party Sharing

- **No developer servers:** Xenon Download Manager runs no backend servers and receives no user data.
- **No selling or advertising:** User data is never sold, rented, transferred to third parties, or used for advertising, profiling, or creditworthiness.
- **No remote code:** All extension code is bundled inside the signed extension package.

## Contact

For privacy questions or security reports, please open an issue at [github.com/gglemas/Xenon-Download-Manager/issues](https://github.com/gglemas/Xenon-Download-Manager/issues).
