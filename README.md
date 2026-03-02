# Re-gret ZMK Module

This is a [ZMK Module](https://zmk.dev/docs/features/modules) for my [Re-gret keyboard](https://github.com/rschenk/re-gret).

To use this in your zmk-config, follow the [ZMK Module docs](https://zmk.dev/docs/features/modules) using the config below. You'll name your keymap `re-gret.keymap`.

## Usage

Add the following entries to `remotes` and `projects` in `config/west.yml`

```yaml
# config/west.yml
manifest:
  remotes:
    - name: zmkfirmware
      url-base: https://github.com/zmkfirmware
    - name: rschenk
      url-base: https://github.com/rschenk
  projects:
    - name: zmk
      remote: zmkfirmware
      import: app/west.yml
    - name: zmk-keyboard-re-gret
      remote: rschenk
      revision: main
  self:
    path: config
```

And then in your `build.yaml` file:

```yaml
# build.yaml
board: ["seeeduino_xiao_ble"]
shield: ["re-gret"]
```
