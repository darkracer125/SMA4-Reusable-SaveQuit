# SMA4 – Reusable Save & Quit

A small ROM patcher for **Super Mario Advance 4: Super Mario Bros. 3** on the Game Boy Advance.

## Why I made this

I was having trouble with my saves disappearing after loading them, and initially thought something was wrong with my cartridge or emulator.

After quite a bit of troubleshooting, I discovered that this is actually how the game was designed to work.

In Super Mario Advance 4, **Save & Quit creates a temporary save**. Once you load that save, the game marks it as used. If you turn off your Game Boy without saving again, you lose that checkpoint.

I found this pretty annoying, so I decided to change it.

This patch prevents the game from marking the temporary save as used. You can load your save as many times as you want, and it will remain available until you save again.

It doesn't autosave or change how the rest of the game works.

## Supported ROMs

| Version | Status |
|---|---|
| USA | Tested and working |
| USA/Australia (Rev 1) | Tested and working |
| Europe | Tested and working |
| Europe (Rev 1) | Tested and working |
| Europe (Rev 1) – Wii U Virtual Console | Tested and working |

The patcher identifies ROMs by their SHA-1 checksum, so filenames don't matter. It also detects already-patched ROMs and rejects unsupported versions.

## How to use it

1. Download `SMA4-Reusable-SaveQuit-Universal-Patcher.html`.
2. Open it in your browser. It works offline.
3. Select your clean `.gba` ROM.
4. Apply the patch and save the modified ROM.

That's it. You can now use the patched ROM in your emulator or on compatible GBA hardware.

I recommend backing up your existing save file before trying it.

## A bit about the fix

I tracked down the problem by comparing save files before and after loading a checkpoint, then using mGBA's debugger to find the instruction responsible.

The game sets a flag when you load a temporary save. The patch changes one Thumb instruction to stop that flag from being set.

The actual save system is left alone.

The European Wii U version has been tested successfully. The other versions use the equivalent instruction change, but I haven't had them all gameplay-tested yet.

If you test another version, feel free to open an issue and let me know whether it works.

## License

Free to download and use. You may redistribute unmodified copies as long as you credit this repository and include a link to it.

Modification requires permission. See [LICENSE](LICENSE) for details.

## Disclaimer

This is an unofficial fan-made patcher and is not affiliated with Nintendo.

No game ROMs are included. You'll need to provide your own copy of Super Mario Advance 4.
