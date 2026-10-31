# Sonu Live GPS — setup notes

## Current preview
Open `index.html` on an HTTPS host (or localhost). Tap **Start sharing my location** and grant browser location permission to see your own GPS position on the map. Tap **Stop** to end updates.

## Important current limitation
This first version is a local-device preview. It does **not** transmit coordinates to other users, and the invite-code box is only a UI preview. Do not treat it as a working multi-person tracker yet.

## Next production step
To enable consent-based cross-device sharing and Android packaging:
1. Create a Firebase project.
2. Enable Authentication (anonymous or phone sign-in) and Cloud Firestore.
3. Add strict Firestore security rules so only accepted friends can read a user's location, and only the owner can write their own location.
4. Add invite acceptance, sharing expiry, and a server-side cleanup policy.
5. Wrap the web app as an Android app (Capacitor) and test background-location behavior with Android permissions.

Never track anyone without their explicit consent. Background GPS on Android requires additional native permissions and Play Store policy compliance.
