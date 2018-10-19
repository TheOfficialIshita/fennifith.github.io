---
layout: docs
title: AppNotificationsPreferenceData Documentation
---
#### [.](./../../../../../../../../../index) > [app](./../../../../../../../../index) > [src](./../../../../../../../index) > [main](./../../../../../../index) > [java](./../../../../../index) > [com](./../../../../index) > [james](./../../../index) > [status](./../../index) > [data](./../index) > [preference](./index) > **AppNotificationsPreferenceData.java**

## [getApps](https://github.com/TheAndroidMaster/Status/blob/master/app/src/main/java/com/james/status/data/preference/AppNotificationsPreferenceData.java#L34)

**Type:** `public` `List<AppPreferenceData>`

Contrary to what one might believe, this does not in fact return the selected apps 
in this preference, but instead returns ALL of the apps on the user's phone. This 
is used to cache the data so that the user doesn't see any more loading bars than 
necessary. This should be done better, I know. It is a planned improvement. 






**Returned Value:** the apps  








