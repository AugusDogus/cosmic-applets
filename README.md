# cosmic-applets (slopfork)

This is an opinionated fork of [pop-os/cosmic-applets](https://github.com/pop-os/cosmic-applets) with specific fixes and features I want as someone coming from Windows. These changes are tailored to my workflow and may not match upstream's design goals.

## Changes from upstream

| Change                                     | Description                                                                                                                                                                                                                 | Upstream Issue                                                |
| ------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------- |
| Fix: Minimize-on-click across monitors     | Clicking a dock icon now correctly minimizes/restores windows regardless of which monitor they're on. Also fixes a focus race condition where clicking the dock would steal focus before the toggle action was processed.   | [#1351](https://github.com/pop-os/cosmic-applets/issues/1351) |
| Feature: Live window preview thumbnails    | Window preview thumbnails in the dock popup update in real-time instead of being a static one-shot screenshot. Uses `ext-image-copy-capture-v1` wait-for-damage semantics so frames are only captured when content changes. | [#858](https://github.com/pop-os/cosmic-applets/issues/858)   |
| Feature: Drag to reorder window thumbnails | Window thumbnails in the dock popup can be reordered via drag and drop, and the reordered preview order syncs across docks on multiple monitors.                                                                            | [#1344](https://github.com/pop-os/cosmic-applets/issues/1344) |

## Quickstart

```sh
git clone https://github.com/AugusDogus/cosmic-applets.git
cd cosmic-applets
just build-release
sudo just install
pkill cosmic-panel # restart COSMIC panel so it picks up the new binaries
```

<sub>When a system update reinstalls the packaged upstream `cosmic-applets`, rerun these steps.</sub>
