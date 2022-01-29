# Presets
These files are used with the `Load Preset` video configuration option to assign a set of options all at once.

## Submission Guidelines
The structure of the Presets folder should remain tidy and easy to navigate. There should be no large "collections" of presets, such as `Old CRT Scanlines 115` followed by `Old CRT Scanlines 110` and etc. Instead, a single option `Old CRT with Scanlines` should be present, with the expectation that the user can then easily tweak the scanlines to their tastes.

When possible, presets should use specific files inside the subdirectories of filters, masks, and etc rather than copies that may be at the top level. The reason for this is that it makes it easier for the user to tweak that setting if they desire, rather than having to navigate further to find alternatives.

System specific presets are fine, such as `Gameboy (mono)`, as well as display-device-specific presets, such as `Sony PVM 20L5`. Please do your best to avoid any excessively obscure or niche devices if possible. If you feel an additional folder is necessary, please discuss it with the maintainers of this repo.

Avoid excessively long names that become difficult to read in the MiSTer's UI. All names should be intuitive and accurately represent the behavior of the preset, within reason.

Above all, remember that Presets are an important part of the user experience. Please create, name, and submit them with a users-first mindset.

## Creating Presets
A preset is a basic INI file, and each file represents a single preset. The structure is straightforward:

```ini
hfilter=Upscaling - Lanczos Bicubic etc/lanczos2_10.txt
vfilter=same
sfilter=off
gamma=gamma_140.txt
mask=VGA.txt
maskmode=2x
```

If a particular setting is not specified the setting will be ignored when the preset is loaded. If the filter/mask/gamma file specified in the preset is not found, the option will be disabled. If the setting is set to `off` it will be disabled, and setting one of the filters to `same` will have the same function as setting them to `same` on the menu.

Each file specified is relative to its base folder, so `shadow_masks` for masks, `Gamma` for gamma, and etc.

The current options are:
|Name|Description|
|----|-----------|
|hfilter|Horizontal polyphase filter file, 'off', or 'same'.|
|vfilter|Vertical polyphase filter file, 'off', or 'same'.|
|sfilter|Scandoubler-specific polyphase filter file, 'off', or 'same'.|
|gamma|Gamma curve file or 'off'|
|mask|Shadow/Pattern mask file or 'off'.|
|maskmode|Any of the selectable options from the shadow mask video setting.|
