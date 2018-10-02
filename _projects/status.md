---
layout: project
type: android-app
title: "Status"
description: "A no-root status bar replacement for Android."
repo: TheAndroidMaster/Status
git: git://github.com/TheAndroidMaster/Status.git
links:
  - name: GitHub
    url: https://github.com/TheAndroidMaster/Status
    icon: https://github.com/favicon.ico
  - name: Issues
    url: https://github.com/TheAndroidMaster/Status/issues
    icon: /images/ic/bug.svg
  - name: Apache License 2.0
    url: https://choosealicense.com/licenses/apache-2.0/
    icon: /images/ic/copyright.svg
  - name: Google Play
    url: https://play.google.com/store/apps/details?id=com.james.status
    icon: /images/ic/play-store.svg
  - name: Status.apk (v3.8-beta5 unstable)
    url: https://github.com/TheAndroidMaster/Status/releases/download/v3.8-beta5/Status.apk
    icon: /images/ic/download.svg
contributors:
  - login: TheAndroidMaster
    avatar: https://avatars1.githubusercontent.com/u/13000407?v=4
    url: https://github.com/TheAndroidMaster
  - login: Technologx
    avatar: https://avatars3.githubusercontent.com/u/17693282?v=4
    url: https://github.com/Technologx
  - login: opnay
    avatar: https://avatars2.githubusercontent.com/u/1689721?v=4
    url: https://github.com/opnay
---

Status is a status bar replacement that draws an overlay on top of the system-generated status bar. This means that the actual status bar is only hidden under the replacement; touch gestures are not overridden, and the standard notification panel is still shown. It needs a lot of permissions in order to obtain the information needed to display in the status bar. These are listed below.

Special thanks to the contributors that have helped to design the app, fix issues, and translate it to different languages:
- [Anas Khan](https://twitter.com/MAKTHG): designed the app icon & helped with UI
- [Vukašin Anđelković](https://dribbble.com/zavukodlak): made a couple status bar icons
- [Ghost Ninja](https://technologx.com/): also made some status bar icons
- [Eugenio Martinez Seguin](https://github.com/Ryo567): Spanish translations
- [Kim Inseop](https://github.com/opnay): Korean translations
- Majida Whale: Chinese translations
- [Marwan ALsidi](https://github.com/Alsidi-Group): Arabic translations

## Permissions
- Accessibility Service: used to attempt to get the status bar color of the current app if the 'status bar coloring' preference is enabled.
- Notification Access: used to get the icons of the current notifications.
- System Alert Window, System Overlay Window: used to draw the status bar above all other apps.
- Battery Stats: used to find if the battery is charging and what percent it is at.
- Network State, Phone State: gets the type and connection of the phone network, and if airplane mode is enabled.
- Wifi State: finds if wifi is enabled and how good the connection is.
- Bluetooth: find if bluetooth is enabled & connected or not.
- Location Services: finds if GPS is enabled.
- Alarm: find if an alarm is set.
- External Storage: backup/restore all settings from a file.

## Contributing
### Issues
Okay, there aren't really any guidelines over issue formatting provided that you don't create issues that already exist, test the app throughly before creating an issue (ex: try clearing the app data), and don't create issues like "It's pointless, just use root". You're not helping.

### Pull Requests
Contributions are accepted. See [CONTRIBUTING.md](https://github.com/TheAndroidMaster/Status/blob/master/./.github/CONTRIBUTING.md) for more information.

### Icons
There used to be a list of all the possible icon formats here to use as a reference, but I stopped updating it and it's pretty useless now. If you want to make status bar icons to add to this app, either [contact me](mailto:contact@jfenn.me) or look in the repository for the existing icon files.

## License

```
Copyright 2018 James Fenn

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
