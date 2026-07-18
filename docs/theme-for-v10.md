# ImageGlass 10 Theme Packs

Customize the appearance of ImageGlass by creating your own theme pack. An ImageGlass theme pack is an archive file with the `.igtheme.zip` extension. Because it ends in `.zip`, you can open it directly with any archive viewer, or File Explorer on Windows.

> 💡 This guide covers the theme pack format for ImageGlass 10. If you are building a theme for ImageGlass 9, refer to [Create a theme for ImageGlass 9](https://github.com/ImageGlass/Theme/blob/main/docs/theme-for-v9.md) instead.

## Theme Pack Structure

A theme pack folder should contain the following:

- One `igtheme.json` file. This essential file stores all theme settings and lets ImageGlass recognize the theme pack.
- One theme preview image file. ImageGlass shows this image as a theme preview in the Settings dialog.
- SVG icon files for toolbar icons, the app logo, and other visual elements.

All of these files should sit in a folder named `THEME_FOLDER`. The structure should resemble the following:

```
THEME_PACK.igtheme.zip
  |- THEME_FOLDER
    |- igtheme.json
    |- theme preview image file
    |- SVG icon files...
```

The `THEME_FOLDER` should follow this naming convention:

```
<theme-name>.<author-name>
```

where:

- `theme-name` is the name of the theme, with words separated by hyphens `-`.
- `author-name` is the name of the author, with words separated by hyphens `-`.

For example: `Kobe.Duong-Dieu-Phap`, `2017-Light-Gray.Duong-Dieu-Phap`.

`THEME_PACK.igtheme.zip` follows a similar convention, with the extension:

```
<theme-name>.<author-name>.igtheme.zip
```

For example: `Kobe.Duong-Dieu-Phap.igtheme.zip`, `2017-Light-Gray.Duong-Dieu-Phap.igtheme.zip`.

## Create a Theme Pack

### Step 1. Create the Theme Pack Folder Structure

### Step 2. Create the `igtheme.json` File

This is the most important file in the theme pack. It provides all the necessary SVG icon files to ImageGlass, along with other theme information. The file is in JSON format, detailed as follows:

```ts
{
  "_Metadata": { // see step 2.1
    "Description": "ImageGlass theme configuration file",
    "Version": 10
  },
  "Info": {
    ... // see step 2.2
  },
  "Settings": {
    ... // see step 2.3
  },
  "Colors": {
    ... // see step 2.4
  },
  "ToolbarIcons": {
    ... // see step 2.5
  }
}
```

> 💡 For a complete example of the `igtheme.json` file, refer to [Green-Gradient.Duong-Dieu-Phap/igtheme.json](https://github.com/ImageGlass/Theme/blob/main/themes/dark/Green-Gradient.Duong-Dieu-Phap/igtheme.json).

#### 🟢 Step 2.1: Section `_Metadata`

Provides the metadata of the ImageGlass theme pack. Do not alter this section.

| Key name      | Value                                   | Description                                                                                                             |
| ------------- | --------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| `Version`     | `10`                                    | Spec version of the configuration file. ImageGlass uses this to check that the theme pack is compatible. Leave it as is |
| `Description` | `"ImageGlass theme configuration file"` | A constant description (do not change it)                                                                               |

#### 🟢 Step 2.2: Section `Info`

Provides basic information about your theme pack.

| Key name      | Example value                              | Description                                                  |
| ------------- | ------------------------------------------ | ------------------------------------------------------------ |
| `Name`        | `"Moon light"`                             | The name of your theme, visible in the ImageGlass theme list |
| `Version`     | `1.0`                                      | The version number of your theme (a number, not a string)    |
| `Description` | `"A Moon light dark theme for ImageGlass"` | A short description of your theme                            |
| `Author`      | `"Duong Dieu Phap"`                        | The author who created this theme pack (optional)            |
| `Email`       | `"phap@example.com"`                       | The author's contact email (optional)                        |
| `Website`     | `"https://example.com"`                    | The author's website (optional)                              |

#### 🟢 Step 2.3: Section `Settings`

Provides general settings for your theme pack.

| Key name       | Example value    | Description                                                                                     |
| -------------- | ---------------- | ----------------------------------------------------------------------------------------------- |
| `IsDarkMode`   | `true`           | Theme pack color mode; the default value is `true`. A light theme pack must set this to `false` |
| `AppLogo`      | `"logo.svg"`     | The logo of ImageGlass, displayed on the title bar of all windows                               |
| `PreviewImage` | `"preview.webp"` | The preview image of the theme pack; WebP and JPG are recommended                               |

> 💡 The left and right navigation arrow buttons use the `ViewPreviousImage` and `ViewNextImage` icons from the `ToolbarIcons` section (step 2.5).

#### 🟢 Step 2.4: Section `Colors`

Defines the base color scheme of ImageGlass. You only need to provide a handful of base colors; ImageGlass automatically derives the rest (hover, pressed, and selected states for toolbar buttons, gallery thumbnails, and menu items, plus navigation buttons and borders) from these base colors and the accent color.

All colors should be in HEX code (web format), including alpha values. Example: `#fff`, `#fffa`, `#ffffff`, `#ffffffaa`, and so on.

| Key name         | Example value | Description                                                                                                                                         |
| ---------------- | ------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| `AccentColor`    | `""`          | The accent color of the theme. Leave it empty (`""`) to follow the system accent color, or set a HEX value (e.g. `"#0078d4"`) to use a fixed accent |
| `TextColor`      | `"#dedede"`   | Text color of the viewer                                                                                                                            |
| `BgColor`        | `"#151b1faa"` | Background color of the viewer                                                                                                                      |
| `ToolbarBgColor` | `"#151b1f00"` | Background color of the toolbar                                                                                                                     |
| `GalleryBgColor` | `"#151b1f00"` | Background color of the gallery                                                                                                                     |
| `MenuBgColor`    | `"#1e2429"`   | Background color of the menu                                                                                                                        |

Every color above (except `AccentColor` itself) can also reference the resolved accent color:

- Use `"accent"` as the color value to use the accent color as is.
- Use the `accent:<alpha>` syntax to adjust its opacity. The `alpha` value ranges from `0` to `255`. Example: `"accent:70"`.

#### 🟢 Step 2.5: Section `ToolbarIcons`

Provides icons for the toolbar. All icon files should be in SVG format for better scaling on high-DPI screens.

| Key name            | Example value             | Description                                                               |
| ------------------- | ------------------------- | ------------------------------------------------------------------------- |
| `ActualSize`        | `"ActualSize.svg"`        | The "Actual size" button                                                  |
| `AutoZoom`          | `"AutoZoom.svg"`          | The "Auto zoom" button                                                    |
| `Checkerboard`      | `"Checkerboard.svg"`      | The "Checkerboard" button                                                 |
| `ColorPicker`       | `"ColorPicker.svg"`       | The "Color picker" button                                                 |
| `Crop`              | `"Crop.svg"`              | The "Crop image" button                                                   |
| `Delete`            | `"Delete.svg"`            | The "Move to the Recycle Bin" button                                      |
| `Edit`              | `"Edit.svg"`              | The "Edit" button                                                         |
| `Exit`              | `"Exit.svg"`              | The "Exit" button                                                         |
| `Export`            | `"Export.svg"`            | The "Export" button when the "Page navigation" tool is open               |
| `FlipHorz`          | `"FlipHorz.svg"`          | The "Flip horizontal" button                                              |
| `FlipVert`          | `"FlipVert.svg"`          | The "Flip vertical" button                                                |
| `FullScreen`        | `"FullScreen.svg"`        | The "Full screen" button                                                  |
| `Gallery`           | `"Gallery.svg"`           | The "Gallery" button                                                      |
| `LockZoom`          | `"LockZoom.svg"`          | The "Lock zoom ratio" button                                              |
| `MainMenu`          | `"MainMenu.svg"`          | The "Main menu" button                                                    |
| `OpenFile`          | `"OpenFile.svg"`          | The "Open file" button                                                    |
| `Pause`             | `"Pause.svg"`             | The "Pause" button when the "Page navigation" tool is open                |
| `Play`              | `"Play.svg"`              | The "Play" button when the "Page navigation" tool is open                 |
| `Print`             | `"Print.svg"`             | The "Print" button                                                        |
| `Refresh`           | `"Refresh.svg"`           | The "Refresh" button                                                      |
| `RotateLeft`        | `"RotateLeft.svg"`        | The "Rotate left" button                                                  |
| `RotateRight`       | `"RotateRight.svg"`       | The "Rotate right" button                                                 |
| `Save`              | `"Save.svg"`              | The "Save image" button                                                   |
| `ScaleToFill`       | `"ScaleToFill.svg"`       | The "Scale to fill" button                                                |
| `ScaleToFit`        | `"ScaleToFit.svg"`        | The "Scale to fit" button                                                 |
| `ScaleToHeight`     | `"ScaleToHeight.svg"`     | The "Scale to height" button                                              |
| `ScaleToWidth`      | `"ScaleToWidth.svg"`      | The "Scale to width" button                                               |
| `Slideshow`         | `"Slideshow.svg"`         | The "Slideshow" button                                                    |
| `ViewFirstImage`    | `"ViewFirstImage.svg"`    | The "View the first frame" button when the "Page navigation" tool is open |
| `ViewLastImage`     | `"ViewLastImage.svg"`     | The "View the last frame" button when the "Page navigation" tool is open  |
| `ViewNextImage`     | `"ViewNextImage.svg"`     | The "View next image" button                                              |
| `ViewPreviousImage` | `"ViewPreviousImage.svg"` | The "View previous image" button                                          |
| `WindowFit`         | `"WindowFit.svg"`         | The "Window fit" button                                                   |
| `ZoomIn`            | `"ZoomIn.svg"`            | The "Zoom in" button                                                      |
| `ZoomOut`           | `"ZoomOut.svg"`           | The "Zoom out" button                                                     |

### Step 3. Copy Icon and Image Files to the Theme Folder

### Step 4. Add a Theme Preview Image File as Specified in Step 2.3

### Step 5. Pack Your Theme

Rename your theme folder to match the naming convention, compress the whole theme folder into a `.zip` file, then rename it so it ends with `.igtheme.zip`.

Example: `Moon-light.Duong-Dieu-Phap.igtheme.zip`.

### Step 6. Share Your Theme

After creating an impressive theme, share it with others by opening [an issue here](https://github.com/ImageGlass/theme/issues) and attaching your theme pack.
