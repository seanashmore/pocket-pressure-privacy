# Privacy Policy for Pocket Pressure

_Last updated: 2026-09-30_

## The short version

Pocket Pressure doesn't collect your data. It has no server, no account, no analytics and no ads, and nothing you enter is ever sent anywhere by the app. Everything you enter stays on your device, encrypted, until you delete it or uninstall the app. The one optional exception is Health Connect export, which you can turn on to copy your readings into Android's own on-device health store (see below).

The app offers an optional one-time "Premium" purchase through Google Play. That purchase is handled by Google Play, not by us, and it's the only reason the app has internet permission at all (see "Google Play purchases" below). Your readings and settings are never part of it.

A privacy policy for an app that collects nothing is an unusual thing to write, but Google Play requires one regardless of what a developer does or doesn't collect, so here it is — stated plainly rather than as boilerplate that doesn't reflect how the app actually works.

## What Pocket Pressure stores, and where

Pocket Pressure is a blood pressure tracking app. When you use it, it stores the following **only on your device**:

- Blood pressure readings you enter: systolic, diastolic, pulse, date, time, and optionally which arm, body position, and a free-text note
- App settings: reminder time, theme, whether App Lock and Health Connect export are enabled
- Profiles: each reading belongs to a profile. Every installation has one profile for you; with Premium you can add more (for example a partner or parent). A profile holds a name, a colour and icon you pick for its avatar, and optionally a date of birth, a medication list and a target range that you type in. They are stored in the same encrypted database as your readings and are only printed on a report you choose to share. If you keep readings for someone else, that is your choice and your responsibility: the app treats every profile the same way and never sends any of it anywhere.
- If you enable App Lock: a cryptographic hash of your PIN (never the PIN itself)

This data is held in a local database that is **encrypted at rest** (SQLCipher, with the encryption key protected by your device's hardware-backed Android Keystore). The app also opts out of Android's automatic cloud backup and device-to-device transfer, so none of this data is ever copied off your device by the operating system either. This also means your readings don't move to a new phone automatically — export them as a CSV and import that file on the new device.

## What Pocket Pressure does *not* do

- **No data transmission of its own.** Pocket Pressure has no backend and no code that sends your readings, settings or anything else you enter anywhere — not to us, not to any third party. The only network activity in the app comes from Google Play's billing library, used for the optional Premium purchase (see "Google Play purchases" below).
- **No analytics.** No usage tracking, no event logging, no third-party analytics SDK of any kind.
- **No crash reporting SDK.** Pocket Pressure doesn't bundle Crashlytics, Sentry, or anything similar. If Google Play's own built-in Android Vitals surfaces a crash report from your device, that's Google's platform-level service, operated by Google under its own privacy terms — not something this app collects or has access to.
- **No accounts.** There's no sign-up, no login, no user identity of any kind tied to your data.
- **No third-party data sharing.** Pocket Pressure doesn't share your data with any third party. The only third-party service it integrates with is Google Play's billing, for the optional Premium purchase (below). Health Connect (below) is part of Android itself, runs on your device, and is only used if you turn it on.

## Google Play purchases (optional)

Pocket Pressure is free, with an optional one-time **Premium** purchase that unlocks extras such as the full doctor report with your details, Insights, multiple profiles, multiple reminders, home screen widgets and custom themes. Health Connect sync, basic PDF export and the alternate app icons are free. There is no subscription and no account.

- **Who handles it:** the purchase is processed entirely by Google Play, under [Google's privacy policy](https://policies.google.com/privacy). We never see your payment details, and there's no Pocket Pressure server involved — we don't receive or store anything about you from it.
- **What the app keeps:** a single on-device yes/no flag recording whether Premium is unlocked, so it keeps working offline. On launch and when you open the Premium screen, the app asks Google Play (on your device) whether you own Premium, to pick up a purchase made on another device or to reflect a refund.
- **Why the app has internet permission:** Google Play's billing library, which any app selling through Google Play must include, bundles a Google component that can send Google diagnostic information about billing operations. That component adds Android's internet permission to the app. Pocket Pressure's own code never uses the network, and none of your readings, notes or settings are sent.

## Health Connect (optional, off by default)

If you turn on **Settings → Data → Health Connect**, Pocket Pressure writes your readings to [Health Connect](https://developer.android.com/health-and-fitness/guides/health-connect), Android's on-device store for health data:

- **What is written:** for your own (primary) profile only, each reading's systolic and diastolic pressure, date and time, arm and body position (if recorded), and pulse (if recorded) as a heart rate entry. Notes are not written.
- **Write-only:** Pocket Pressure never reads any data from Health Connect.
- **Stays on your device:** Health Connect is part of Android, not a server. Pocket Pressure sends nothing to us or anyone else. Other apps can read these readings from Health Connect only if you separately grant them permission in Health Connect.
- **Your control:** you can turn export off in Pocket Pressure at any time, which stops new writes, and revoke Pocket Pressure's access or delete its data from Health Connect's own settings.

The data written to Health Connect is used only to make your readings available to you in Health Connect. It is not used for advertising, sold, or transferred for any other purpose.

## Home screen widgets (optional, Premium)

If you add a Pocket Pressure widget to your home screen, it can show your latest reading for the profile you chose when you placed it. By default the reading is hidden on the widget while App Lock is on; you can change that in Settings. Widgets are drawn on your device by the app and send nothing anywhere.

## Permissions

Pocket Pressure requests these Android permissions:

- **Notifications (`POST_NOTIFICATIONS`)** — used solely to show your daily reading reminder, if you enable it in Settings. This permission does not give the app any access to your data; it only lets it display a local notification.
- **Biometrics and fingerprint (`USE_BIOMETRIC`, `USE_FINGERPRINT`)** — only used if you turn on App Lock and choose to unlock with your fingerprint or face. The app never receives your biometric data; Android tells it only whether the check succeeded.
- **Write blood pressure and write heart rate to Health Connect (`health.WRITE_BLOOD_PRESSURE`, `health.WRITE_HEART_RATE`)** — only requested if you turn on Health Connect export, and used only as described above. Pocket Pressure requests no permission to read health data.
- **Google Play billing and internet (`com.android.vending.BILLING`, `INTERNET`, `ACCESS_NETWORK_STATE`)** — added automatically by libraries the app includes (Google Play's billing library, and Android's WorkManager background-task library, which schedules reminders). Pocket Pressure's own code never uses them to send anything; the only network use is Google Play billing, as described above. These are granted at install time; Android doesn't ask you about them.
- **Background tasks (`WAKE_LOCK`, `RECEIVE_BOOT_COMPLETED`, `FOREGROUND_SERVICE`)** — also added by the WorkManager library: they let Android wake the app at the time of a reminder and restore your reminders after the phone restarts. They give the app no access to your data.

## Your data, your control

Because nothing is stored anywhere but your own device:

- You can export your readings as a CSV file at any time (Settings → Data → Export as CSV), for your own records or to share with a healthcare provider, and import a CSV back in. With several profiles you choose which profile an import or export is for.
- Deleting a profile deletes its readings and reminders immediately and permanently.
- Deleting a reading in the app deletes it immediately and permanently — there is no server copy to also remove.
- **Uninstalling the app deletes everything.** There is no account to close and no server-side data to separately request deletion of, because none exists.

## Children's privacy

Pocket Pressure is a general-purpose health-tracking utility, not directed at children, and collects no data from anyone regardless of age.

## Changes to this policy

If this policy changes, an updated version will be published at the same location with a new "last updated" date. The app's no-server, no-collection design for your health data is a fundamental design choice rather than an incidental current state, so no change here should be expected to weaken it — but the date at the top is the way to confirm what's current.

## Contact

Questions about this policy or the app can be sent to:

**littlelostprojects@gmail.com**
