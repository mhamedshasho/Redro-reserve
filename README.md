# Redro Reserve

Open-source, offline-first PWA for managing reservations for tables, PlayStation stations, rooms, and other resources.

## Principles

- GitHub Pages hosting and GitHub Actions deployment.
- No backend, cloud database, external API, or analytics.
- Local IndexedDB storage on each device.
- Offline app shell through a service worker after the first successful load.
- Manual JSON backup and restore.
- Redro red/white light identity and red/black dark identity.
- No financial accounting and no reminder notifications.

## Offline behavior

Each device has its own independent local database. There is no automatic synchronization or shared live booking calendar between devices. A manual backup can be exported and imported to move data.

The PWA must be loaded once while online from GitHub Pages before it can be used offline. Browser storage can still be cleared, so regular manual backups are recommended.

Audio alarms require the app to be open and the browser to permit audio playback. Mobile operating systems may suspend background tabs or closed PWAs; alarms are not guaranteed while suspended or closed.

## Deployment

GitHub Actions deploys the repository root to GitHub Pages on every push to main. In repository Settings, open Pages and select GitHub Actions as the build and deployment source if it is not selected automatically.

## Storage

IndexedDB stores resources, bookings, and preferences. No user data is sent to a server by the application.
## Quick usage

1. Add reservable resources in **Tables & devices**.
2. Create bookings with a start/end time or a start time and duration.
3. The app rejects same-resource overlaps on the same day. Overnight bookings are not supported.
4. Acknowledge end-time alarms to stop repeat alerts. While enabled, alarms repeat every 45 seconds until acknowledged.
5. Export JSON backups regularly. Use Replace or Merge when restoring.

The application has no external API or cloud service. IndexedDB data belongs to the current browser/device and is not synchronized automatically. Keep the app open and allow audio for alarms; closed or suspended PWAs cannot guarantee alerts.
