# AndroidSmsGateway (Dual-SIM + QR)
Android app that polls your server for queued SMS and sends via the device's SIM(s). Now with QR provisioning and SIM selection.

## How to use
1. Open in Android Studio and run on a real device.
2. Tap **Scan QR** and scan text like:
   `api_key=YOUR_KEY&server=https://sms.mafia-assassins.co.uk`
   (JSON also supported: `{"api_key":"...","server":"https://..."}`)
3. Choose the **SIM** to send from, tap **Save**.
4. Tap **Run Now** or wait ~15 minutes for background polling.

## Permissions
- SMS sending, Phone state, Camera (for QR), Internet.

## Notes
- Uses CameraX + ML Kit for QR.
- Uses `SubscriptionManager` to list SIMs. Stores selected `subscriptionId`.
- `SmsManager.getSmsManagerForSubscriptionId(subId)` sends via chosen SIM.
