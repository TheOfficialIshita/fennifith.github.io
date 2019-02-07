---
layout: "project"
type: "android-app"
title: "Media Notification"
description: "Slightly unstable attempt to replace all media notifications with Android O styled copies."
icon: "https://raw.githubusercontent.com/fennifith/MediaNotification/master/app/src/main/ic_launcher-web.png"
repo: "fennifith/MediaNotification"
git: "git://github.com/fennifith/MediaNotification.git"
links: 
  - name: "GitHub"
    url: "https://github.com/fennifith/MediaNotification"
    icon: "https://github.com/favicon.ico"
  - name: "Issues"
    url: "https://github.com/fennifith/MediaNotification/issues"
    icon: "/images/ic/bug.svg"
  - name: "Apache License 2.0"
    url: "https://choosealicense.com/licenses/apache-2.0/"
    icon: "/images/ic/copyright.svg"
  - name: "Google Play"
    url: "https://play.google.com/store/apps/details?id=james.medianotification"
    icon: "/images/ic/play-store.svg"
  - name: "MediaNotification.apk (v1.0 stable)"
    url: "https://github.com/fennifith/MediaNotification/releases/download/v1.0/MediaNotification.apk"
    icon: "/images/ic/download.svg"
contributors: 
  - login: "fennifith"
    avatar: "https://avatars1.githubusercontent.com/u/13000407?v=4"
    url: "https://github.com/fennifith"
  - login: "BrianValente"
    avatar: "https://avatars3.githubusercontent.com/u/3992081?v=4"
    url: "https://github.com/BrianValente"
  - login: "fython"
    avatar: "https://avatars2.githubusercontent.com/u/3166782?v=4"
    url: "https://github.com/fython"
  - login: "jahirfiquitiva"
    avatar: "https://avatars0.githubusercontent.com/u/10360816?v=4"
    url: "https://github.com/jahirfiquitiva"
screenshots: 
  - "https://raw.githubusercontent.com/fennifith/MediaNotification/master/.github/images/settings.png"
  - "https://raw.githubusercontent.com/fennifith/MediaNotification/master/.github/images/colors.png"
  - "https://raw.githubusercontent.com/fennifith/MediaNotification/master/.github/images/apps.png"
languages: 
  - "Java"
isDocs: "true"
isWiki: "false"
pushed: "2019-01-08T16:25:31Z"
---

MediaNotification is a slightly unstable attempt to create Android O styled media notifications. Please note that this app does not replace media notifications coming from other apps, but it creates new notifications on its own. The most common methods of use are as follows:

**Option One**
Leave the original music player notifications intact. The app will read its data and create a new notification with fully operational album art and media controls. There should not be any issues using the app this way, provided that the 'Use Broadcast Receiver' switch is disabled. If you are using this option on Android Nougat or above, it is reccomended to use the power notifications settings (can be enabled in SystemUI Tuner) to show the music player's notification at the bottom of the list and hide the icon from the status bar (change the setting to "1". Setting it to "0" will have the same effect as option two). This has been tested and is working properly on the following music players:
  - Bandcamp
  - BlackPlayer
  - Google Chrome (yes, the web browser)
  - Google Play Music
  - Jair Player
  - Phonograph
  - PlayerPro
  - Pulsar
  - Poweramp
  - Retro Player
  - Shuttle
  - Soundcloud
  - Spotify

**Option Two**
Block all notifications from the music players installed on your phone, and enable the switch at the bottom of the settings menu. The app will then obtain all its information from a BroadcastReceiver, and get the album art from either the external storage (if the song is being played locally) or from the last.fm api. When used with this option, the only music player for which the notification still functions completely is Spotify. Most other apps will have problems with the player controls (player controls for unsupported apps are disabled by default, check the 'Media Controls Method' setting) and content intents (when the notification is clicked on). However, there are a few apps for which the content intents still function properly:
  - BlackPlayer
  - Phonograph
  - Timber
  - Jockey
  - Jair Player
  - Pulsar
  - NewPipe

As a sort of workaround, it is possible to set a 'Default Music Player' for the notification to open if it cannot obtain a content intent any other way.

**IMPORTANT:** The following music players require their settings to be modified in order to work properly:
  - Spotify: Enable "Device Broadcast Status" in the settings menu.
  - Shuttle: Turn on last.fm scrobbling (you don't need to download a scrobbler).
  - AIMP: The 'integrate to lock screen' setting must be enabled
  - Jair Player: 'Enable Scrobbling' at the bottom of the settings menu. You will need to install the scrobbler app in order for this to work (uninstalling it will disable the setting).
  - NewPipe: support for this player does exist, but is very limited. It is reccomended to turn on 'Use external audio player' in NewPipe's settings menu instead.
  - BlackPlayer: Turn on the 'Scrobble Music' setting (at the bottom of the 'Metadata' section). You do not need to have a scrobbler installed.

**Option Three**
Somehow install the app on the system partition of your device, and grant it `android.permission.UPDATE_APP_OPS_STATS`. This is not possible to do from within the app as the `UPDATE_APP_OPS_STATS` permission is protected by the application signature. In other words, you will need to compile a new apk with the same signature as the rest of the system apps first. I am working on a way to bypass this permission and make the third option function with just root access, but it will be a while before it is finished.

---

Unfortunately, this app does not function at all when used with the following music players. This is simply because they either do not use the MediaPlayer API, or they do use it and have prevented other apps from intercepting any information from it.
  - iHeartRadio
  - Rocket Player
