# TokenUse for Mac — releases

Signed builds and the update feed for the **direct edition** of
[TokenUse for Mac](https://tokenuse.ai/mac), the free menu bar companion to the TokenUse
CLI and dashboard. Installed copies update themselves from here.

## Install

1. Download **[TokenUse.dmg](https://github.com/TokenUse/tokenuse-mac-releases/releases/latest/download/TokenUse.dmg)**
   (or from [tokenuse.ai/mac](https://tokenuse.ai/mac)). Requires macOS 14 or later, Apple silicon or Intel.
2. Open it and drag **TokenUse** into **Applications**.
3. Open TokenUse from Applications. It isn't notarized by Apple yet, so macOS blocks the
   first launch: click **Done**, then open **System Settings → Privacy & Security**, find
   "TokenUse was blocked…", click **Open Anyway** and confirm. (On macOS 14 you can instead
   Control-click the app → **Open** → **Open**.) You only do this once.
4. Click the gem in the menu bar → **Sign in**, and approve the code in your browser. Any
   TokenUse account works, including the free Hobby plan.

Keep the app in Applications — copies run from Downloads or the disk image can't update
themselves.

## Verifying

- Every update archive and the feed
  (`releases/latest/download/appcast.xml`) are signed with TokenUse's EdDSA key, and the
  app verifies both before installing anything.
- The app is signed with TokenUse's code-signing certificate, SHA-1
  `F5450F4F29E2A64A1A03ABAC6F2FE6F6700C6699`. Check a copy with
  `codesign -dv --verbose=4 /Applications/TokenUse.app` (Authority=TokenUse) and
  `codesign -d -r- /Applications/TokenUse.app`.

The app's source is private; this repository only hosts release artifacts.
Questions: support@tokenuse.ai
