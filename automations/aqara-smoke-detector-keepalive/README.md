# Aqara smoke detector keep-alive

*Minimum required version of Home Assistant: 2024.10.0*

**Feature excerpt:**

- ✅ Tries to keep the smoke detector alive for faster reaction time

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/dagobert/homeassistant-blueprints/blob/stable/automations/aqara-smoke-detector-keepalive/aqara-smoke_detector-keepalive.yaml)

## Introduction

This automation toggles the heartbeat indicator switch of the Aqara smoke detectors to force them to keep-alive for a faster reaction to software self-tests, alarm and mute commands.
