# Aqara Smoke Detector Linker (Test and Alarm)

*Minimum required version of Home Assistant: 2024.10.0*

**Feature excerpt:**

- ✅ Notification driven self-tests of all detectors by one "click"
- ✅ Real-Fire-Alarm test (uses the same path as on smoke detections)
- ✅ First-Alarm notification to allow preventing false alarm propagation
- ✅ Fire-Alarm propagation to all detectors
- ✅ Persistant Fire-Alarm notification
- ✅ Fire-Alarm Text-to-Speech (TTS) notification
- ✅ Mute Alarm action on notification
- ✅ Action on alarm
- ✅ Wakeup detectors on tests and alarm

[Subscribe to this Issue](https://github.com/dagobert/homeassistant-blueprints/issues/1) to stay up-to-date since Home Assistant has no facility to manage blueprint updates. Updates are only posted if there are functional changes or new features. 

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/dagobert/homeassistant-blueprints/blob/stable/automations/aqara-smoke-detector-linker/aqara-smoke_detector-linker-testandalarm.yaml)

🔺 It is recommended to use the [Aqara Smoke Detector Keep-alive](https://github.com/dagobert/homeassistant-blueprints/tree/stable/automations/aqara-smoke-detector-keepalive) blueprint additionally. 🔺

## Introduction

This blueprint automation allows you to link the Aqara Smoke Detector JY-GZ-01AQ because it does not link itself to eachother directly even the official documents might lead you to this conclusion. Linking is either done by the Aqara hub or has to be implemented in your home automation system.

This blueprint is inspired by the following blueprint creations. Thanks to these developers. [ciB](https://community.home-assistant.io/t/aqara-smoke-detector-linkage-alarm/517656), [vansummeren](https://community.home-assistant.io/t/aqara-smoke-detector-linkage-alarm-plus-optional-actions/750785)

### Self-Tests

To test your smoke alarm devices you can conduct a self-test by using either the hardware button on a device or use the software self-test button. When using the hardware button you need to hold it for at least 3 seconds and continue a few more after the test started. The hardware button is not relyable probably because of the deep sleep capability of the device.

During this self-test you will receive mobile notifications that ask you to continue the self-test of ever associate smoke detector one-by-one. You will have time in between to advanve to the next detector. The assigned area will be shown in the notification.

<strong>🔆</strong> When selecting the smoke detectors here in the automation you should order them in a way that makes it easy for you to go from one to the next efficiantly.


### Fire-Alarm Test

This automation implements a fake fire alarm test. You can disable this test in the settings if you do not want to use this feature instead using special testing gas.

After the self-test you will be asked to conduct a "real" fire alarm test. This alarm uses the same sequence as if a smoke detector triggers this automation by detecting smoke. This is a special feature of this blueprint since using using seperate sequences would not serve the purpose at all.

To avoid confusion you should definetly prepare everyone in your household that you are about to do this test. For recipients of smoke alarm messages these will have a forced prefix and suffix <code>!TEST!</code> in the title.