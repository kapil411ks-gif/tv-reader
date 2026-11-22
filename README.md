# TV Reader

A free screen reader for Android TV / Google TV, in early public (beta) testing.

TV Reader reads the text that apps expose to accessibility services and speaks it aloud, using your TV remote.

## Main features

- **Review Mode.** Explore exposed screen text using your remote. Left/Right reads the previous or next item; Up/Down changes between Control, Character, Word, Sentence, Paragraph, Everything and Link. Webpage reading currently works in normal mode, while webpage Review navigation and access to all page content are still being improved.
- **Everything level.** Left starts reading again from the top of the screen, Right reads from the current item. OK pauses and resumes; after resuming it may repeat the last word or sentence.
- **Quick Controls.** Assign a spare remote button; hold it and release to open a panel. Left and Right choose Volume, Speech rate, Language, Voice or Mute. Up and Down change the value, OK confirms a language or voice, and Back closes the panel. These change the reader's own speech only, not the TV's media volume.
- **Screen Help.** Reads the text on screen that apps expose to accessibility, in one go, without moving focus. It does not read text that apps do not expose, and it does not use OCR.
- **Per-app profiles.** Choose an installed TTS engine, language and voice for each app, without changing the system default. A pinned voice overrides automatic language detection. If a pinned voice is missing, reading may pause.
- **Automatic language detection** across 103 base language codes. You choose the languages to use. It picks between voices installed on your TV; it does not translate or download voices, and it can misjudge some text.
- **Verbosity.** Choose how much is spoken: roles, context, counts, item position, usage hints, punctuation and capital-letter feedback.
- **Keyboard help.** Optional echo of typed characters and words, plus English A-Z examples. Keyboard-symbol announcements are still being worked on.
- **Talking clock.** Off, every 30 minutes, or hourly. It announces only while the TV is awake and the reader service is running.
- **Also included:** configurable shortcuts, optional sound cues with their own volume, a cyan focus border, custom labels for unnamed buttons, settings backup and restore, a remote practice screen and a 15-step tutorial.

You choose the buttons for Review, Quick Controls and Screen Help. If Back is assigned as the Review shortcut, a short press of Back works normally. Android's own accessibility shortcut is separate.

## Recent improvements

Version 1.0.21 fixes the File Manager speech-stopping problem, improves filename reading and includes working media-volume announcements. Browser reading and webpage focus handling have also improved. Existing language switching, per-app voices and the other reader features remain available.

## Install

Requires Android 11 or newer.

**Option 1: from your phone with atvTools.** atvTools (https://atvtools.app/) is a phone app, available on Google Play and the App Store, that installs APK files on your TV over your Wi-Fi network using ADB. No computer is needed.
1. On your phone, install atvTools from Google Play or the App Store.
2. On the TV, open Settings > Device Preferences > About and click Build seven times to show Developer options. In Developer options, enable the debugging mode required by atvTools for your model (USB/network or wireless debugging, where supported).
3. Put your phone and TV on the same Wi-Fi network. Open atvTools on your phone and choose your TV (or add it by its IP address). When the TV asks, allow the connection.
4. Download the TV Reader APK from the Releases page to your phone.
5. In atvTools, open the install option, select the TV Reader APK and install it on the TV. Wait until atvTools shows the installation has finished.
6. Only after TV Reader is installed: on the TV, open Settings > Accessibility > TV Reader and turn the service on.
Menu names differ between TVs. You can turn debugging off again when you finish.

**Option 2: copy the file to the TV.** Copy the APK to your TV with a file-transfer app such as Send Files to TV or LocalSend, or with a USB drive, then open it on the TV to install. These apps only move the file.

**If the accessibility switch is greyed out or shows a "restricted setting" message:** from Android 13, Android can block accessibility for apps installed from a downloaded file. On some devices, App info for TV Reader has an "Allow restricted settings" option (Google's steps: https://support.google.com/android/answer/12623953). Use it if your TV shows it. Menus differ by manufacturer, and some TVs do not have it. Whether another install method, such as atvTools or an installer app like SAI (Split APKs Installer, https://github.com/Aefyr/SAI, a community project that is no longer actively developed), changes this depends on the installer and your TV's firmware. It is not guaranteed.

**Advanced: ADB from a computer.** You can install or update with `adb install -r TV-Reader-1.0.21.apk`. This keeps your settings. It does not enable the accessibility service automatically, and restricted-settings behavior can vary by TV firmware. Allow the connection on the TV, and turn debugging off when you finish. See https://developer.android.com/tools/adb.

**Updates:** install new versions over the old one without uninstalling or clearing data (same package and signing key) to keep your settings. After an update, check that the service is still on.

## Privacy

TV Reader uses accessibility access for reading accessible screen text and controls and for remote navigation. Settings stay in local app storage. Our code review found no app-written persistent screen-reading history, but text is held temporarily in memory while reading. Spoken text goes to your selected TTS engine, which may use the Internet.

Language identification and subtitle processing happen on the device. The bundled Google ML Kit SDK may send diagnostic and usage metadata to Google. We have not measured this release's exact network traffic. Update checks and downloads contact GitHub, which receives connection information including your IP address. Optional update alerts are off by default. No TV Reader account is required.

Accessibility is a powerful permission. TV Reader has not had an independent security audit, and we do not claim it is risk-free. You can disable the service in Android Accessibility settings.

## Known issues

Please read the latest release notes. Webpage reading in Review Mode, reaching all webpage content with the remote, and keyboard-symbol announcements are still being worked on. Some popup text may be missed. Automatic subtitle reading is not working yet; Screen Help may read captions when an app exposes them as accessible text.

If you encounter any issues, please feel free to report them.

## Status

Beta. Issues are enabled on this repository for feedback.

Source code is private for now; only builds and notes are published here.
