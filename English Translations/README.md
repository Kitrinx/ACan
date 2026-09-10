# English translations

IPS patches. Apply each to the matching cartridge from `1 Retail` - the
little-endian files the MiSTer core loads - with any IPS tool.

| Patch | Apply to | Source CRC32 | Result CRC32 | Result size |
|---|---|---|---|---|
| `War of Light Saga - Dragonforce (Taiwan) [T+Eng 1.07].ips` | `War of Light Saga - Dragonforce (Taiwan).bin` | `C4FE1CA1` | `832BECDB` | 3 MB |
| `Child of Evil, The (Taiwan) [T+Eng 0.01].ips` | `Child of Evil, The (Taiwan).bin` | `9F6119A7` | `F31D3904` | 4 MB |
| `Sonic Dragon (Taiwan) [T+Eng 0.01].ips` | `Sonic Dragon (Taiwan).bin` | `F631383C` | `42E1F01D` | 2 MB |

Check the source CRC32 before patching; a different dump will not patch
correctly. The Child of Evil patch grows the cartridge from 2 MB to 4 MB - the
translation needed the room - so the result is twice the size of the source.
Every patch was verified by applying it to the source and comparing the result
byte for byte against the finished ROM.

## Which build each patch produces

Where more than one build of a translation was on the MiSTer, the patch
produces the newest one:

- **Child of Evil** - the 9 September build, CRC32 `F31D3904`. An earlier
  build, CRC32 `5FB41DF1` (7 September), is the one in the `3 Translations`
  folder. The `Child of Evil [T+Eng 0.01].bin` at the top level of the share
  is that same older build under another name.
- **Sonic Dragon** - the 9 September afternoon build, CRC32 `42E1F01D`, which
  was on the MiSTer as `SonicDragonEN.bin`. The `3 Translations` copy is an
  earlier build from that morning, CRC32 `E6F89C23`.
- **War of Light Saga - Dragonforce** - only one build exists, CRC32 `832BECDB`.

The Monopoly translation, `African Expedition [T+Eng 1.00]`, is not included
here yet.
