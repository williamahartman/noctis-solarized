## Noctis-Solarized

The [Noctis](https://github.com/aFFekopp/noctis) theme for Home Assistant, adapted to use the [Solarized Dark](https://ethanschoonover.com/solarized/) color scheme.

## Screenshot
![](https://raw.githubusercontent.com/williamahartman/noctis-solarized/master/docs/screenshots/pc/screenshot.png)

## Installation

#### Manual Installation
1. copy the `themes` folder into your home-assistant folder
2. add this to your `configuration.yaml`

```yaml
frontend:
  themes: !include_dir_merge_named themes
```

3. restart home-assistant
4. select the theme in your user's profile (bottom left)

#### HACS

1. Go to the Community Store.
2. Search for `Noctis-Solarized`.
3. Navigate to `Noctis-Solarized`.
4. Press Install.

#### Fonts

If you want to use the custom fonts:
  - Make sure "Advanced Mode" is enabled in your user settings
  - Go to "Settings" -> "Lovelace Dashboards" -> "Resources"
  - Add a new resource with type "Stylesheet" and this URL: `https://fonts.googleapis.com/css?family=Raleway`

#### Blur

If you want the blur effect on your popup cards you need to have [card-mod](https://github.com/thomasloven/lovelace-card-mod) installed and uncomment the following lines in noctis-solarized.yaml

```yaml
card-mod-theme: noctis-solarized

  card-mod-more-info-yaml: |
    $: |
      .mdc-dialog .mdc-dialog__scrim {
        backdrop-filter: blur(15px);
        -webkit-backdrop-filter: blur(15px);
        background: rgba(0,0,0,.6);
      }
      .mdc-dialog .mdc-dialog__container .mdc-dialog__surface {
        box-shadow: none !important;
        border-radius: var(--ha-card-border-radius);
      }
    .: |
      :host {
        --ha-card-box-shadow: none;
      }
```

(Don't know if necessary anymore) Additionally if you are using Firefox you need to go into `about:config` and set both `gfx.webrender.all`
and `layout.css.backdrop-filter.enabled` to true. You may need to restart Firefox fo it to take effect.
