# Japan-IPTV-EPG

This repository publishes automatically generated EPG data (XMLTV) for Japanese IPTV use.

The generator itself is maintained separately in the `Japan-IPTV-EPG-Generator` repository. Only generated files that pass validation are published here.

## Complete guides.xml

```text
https://raw.githubusercontent.com/Thibi-kuro-Sanboooo/Japan-IPTV-EPG/main/guides.xml
```

The project aims to preserve compatibility with the **244 channels** contained in the karenda-jp reference EPG, including compatible `tvg-id` values, channel names, and channel icons.

## Supported Sources

- ABEMA
- JCOM-based channels
- R Channel
- Fast TV
- SkyPerfect / Bangumi-based channels
- NHK World Premium
- BS10 Premium
- TVer Realtime

Provider-specific XMLTV files and comparison reports are also published separately.

## Updates

The EPG is generated automatically every day with GitHub Actions.

- Scheduled run time: **08:30 JST**
- Default guide window: **2 days**
- The public files are updated only when provider generation, XMLTV validation, 244-channel merging, and compatibility checks all succeed.

The workflow uses a fail-safe design so that a failed or incomplete build does not overwrite the last known-good public EPG.

## Main Files

```text
guides.xml                 Combined 244-channel EPG
guides-parity.md           Full comparison against the karenda-jp reference

abema.xml                  ABEMA
jcom.xml                   JCOM-based channels
rakuten.xml                R Channel
fasttv.xml                 Fast TV
skyperfect.xml             SkyPerfect / Bangumi-based channels
nhkworldpremium.xml        NHK World Premium
bs10premium.xml            BS10 Premium
tver.xml                   TVer Realtime
```

## Project Policy

- Preserve karenda-jp-compatible `tvg-id` values.
- Acquire programme metadata directly whenever possible from official APIs, official programme guides, or other official public data instead of copying a third-party finished EPG.
- Prefer current official programme data, so update timing and title formatting may differ from the karenda-jp reference.
- Do not publish a new build if XMLTV validation or the 244-channel integrity check fails.
- Keep the generator implementation and the public generated data in separate repositories.
