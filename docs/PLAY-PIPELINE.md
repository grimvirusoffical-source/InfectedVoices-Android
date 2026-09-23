# Play pipeline

This repo is the Android shell. The store upload is a later step, and it is not run by the populate commit.

When a real upload happens, do it from the pinned Core checkout:

- follow `core/UPLOAD-ANDROID.md`
- follow `core/PLAY-STORE-READINESS.md` and `core/PLAY-DATA-SAFETY.md`
- application id `space.infectedvoices.studio`
- produce an Android App Bundle for Play
- do not attach that `.aab` or a raw `.apk` to the marketing CDN or to `/get`

`/get` stays store-only: a Google Play link, not a raw bundle.

`npm run sync` stops after `npm run native:android` inside Core. `--submit`, `--upload`, and `--eas` exit 2 while `.secrets/google-play-service-account.json` or `EXPO_TOKEN` is missing, and this populate step still does not upload.
