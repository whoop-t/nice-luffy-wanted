# nice-luffy-wanted

![Preview](https://github.com/whoop-t/nice-luffy-wanted/blob/main/.github/assets/luffywanted.jpg?raw=true)

## Quick setup

In your ZMK firmware, add the following:

Add remote to `west.yaml`
```yaml
manifest:
  remotes:
    - name: zmkfirmware
      url-base: https://github.com/zmkfirmware
    - name: whoop-t #new entry
      url-base: https://github.com/whoop-t #new entry
  projects:
    - name: zmk
      remote: zmkfirmware
      revision: main
      import: app/west.yml
    - name: nice-luffy-wanted #new entry
      remote: whoop-t #new entry
      revision: main #new entry
  self:
    path: config
```

Add this module to `build.yaml`(this is for corne, but change for your keyboard if needed)
```yaml
include:
  - board: nice_nano_v2
    shield: corne_left nice_view_adapter nice_luffy_wanted #update entry
  - board: nice_nano_v2
    shield: corne_right nice_view_adapter nice_luffy_wanted #update entry
```

Also make sure to enable the custom status screen in your ZMK configuration, this would be your keyboards .conf file in the config directory:

```
CONFIG_ZMK_DISPLAY=y
CONFIG_ZMK_DISPLAY_STATUS_SCREEN_CUSTOM=y
```

## Acknowledgements
### Base Repo (for anyone to get started with their own)
https://github.com/whoop-t/nice-shield-base

### Inspiration
https://github.com/M165437/nice-view-gem

### Making the art
https://www.pixilart.com

### Coverting art to C code
https://javl.github.io/image2cpp/

### Other image processing
https://www.iloveimg.com/

