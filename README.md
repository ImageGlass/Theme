🎏 ImageGlass theme packs
==
Everything about [ImageGlass](https://imageglass.org) theme!


[![Total Downloads](https://img.shields.io/github/downloads/ImageGlass/theme/total?color=%233097B8&label=downloads&style=for-the-badge)](https://imageglass.org/themes)


## ⌚ Change history (Version 9)
This instruction is always for the latest version of ImageGlass, for the older versions, please see the changes (if any) at: https://github.com/ImageGlass/theme/releases

If you want to create theme for ImageGlass v8, please refer to [Create-theme-for-v8.md](./Create-theme-for-v8.md).


## 🪐 Naming convention
Please follow this naming convention for your theme folder and theme pack:
### Theme folder (`THEME_FOLDER`)
```xml
<theme-name>.<author>
```

While:
- `theme-name`: The name of the theme, no space, separated by hyphen `-`.
- `author`: The author of the theme, no space, separated by hyphen `-`.

For example: `Kobe.Duong-Dieu-Phap`, `2017-Light-Gray.Duong-Dieu-Phap`.


### Theme pack
Similar to "Theme folder" but with the extension:
```xml
<theme-name>.<author>.igtheme
```

For example: `Kobe.Duong-Dieu-Phap.igtheme`, `2017-Light-Gray.Duong-Dieu-Phap.igtheme`.


## 📂 Theme pack folder structure
A theme pack folder contains:
- 1 `igtheme.json` file
- 1 preview image file
- And SVG icon files

All of these files should be placed in a folder:

```
THEME_FOLDER
|-- igtheme.json
|-- preview image file
|-- SVG icon files...
```

## 🎨 How to create a new theme for ImageGlass 9?
If you look for v8 specs, please refer to [Create-theme-for-v8.md](./Create-theme-for-v8.md).

### 🔵 Step 1. Create theme pack folder structure
### 🔵 Step 2. Create `igtheme.json` file
This is the most important file of the theme, it provides all the SVG icon files to ImageGlass app and other information of your theme.
The structure of `igtheme.json` file is in JSON format, we will go deeper to the detail of each section.
```ts
{
  "_Metadata": { // see step 2.1
    "Description": "ImageGlass theme configuration file",
    "Version": "9.0"
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

#### 🟢 Step 2.1 Section `_Metadata`
Provides the metadata of ImageGlass theme pack. You should not change this section.

Key name | Value | Description
-- | -- | --
`Version` | `"9.0"` | 🚫 Version of configuration file (don't change it).
`Description` | `"ImageGlass theme configuration file"` | 🚫 Just a constant (don't change it).



#### 🟢 Step 2.2 Section `Info`
Provides basic information of your theme packs.

Key name | Example value | Description
-- | -- | --
`Name` | `"Moon light"` | Name of your theme which people will see it in ImageGlass theme list
`Version` | `"1.0"` | The version number of your theme
`Description` | `"A Moon light dark theme for ImageGlass"` | A short description of your theme
`Author` | `"James Black"` | The author who creates this theme pack (optional)
`Email` | `"james.black@gmail.com"` | The contact email of the author (optional)
`Website` | `"https://example.com"` | The website of the author (optional)



#### 🟢 Step 2.3 Section `Settings`
Provides general settings of your theme pack

Key name | Example value | Description
-- | -- | --
`IsDarkMode` | `true` | Theme pack color mode, default value is `true`
`NavButtonLeft` | `"ViewPreviousImage.svg"` | The left arrow navigation button SVG icon
`NavButtonRight` | `"ViewNextImage.svg"` | The right arrow navigation button SVG icon
`AppLogo` | `"logo.svg"` | The logo of ImageGlass, will display on title bar of all windows
`PreviewImage` | `"preview.webp"` | The preview image of the theme pack. Recommended formats: WebP, JPG.



#### 🟢 Step 2.4 Section `Colors`
Provides color scheme of ImageGlass. All colors must be in HEX code (web format), including alpha. Example: `#fff`, `#fffa`, `ffffff`, `ffffffaa`,...

💡 ImageGlass also supports using the system accent color for your theme pack:
- Instead of `"#fff"`, you can use `"accent"`
- You can change the alpha value of the accent color by using this syntax: `<accent>:<alpha>`. The `alpha` value must be in range from `0` to `255`. Example: `"accent:70"`.

Key name | Example value | Description
-- | -- | --
`BgColor` | `"#151b1f00"` | Background color of the viewer
`TextColor` | `"#d3d3d3"` | Text color of the viewer
`ToolbarBgColor` | `"#1E242900"` | Background color of toolbar
`ToolbarTextColor` | `"#dedede"` | Text color of toolbar button
`ToolbarItemHoverColor` | `"#ffffff33"` | Background color of toolbar button when it's hovered
`ToolbarItemActiveColor` | `"#ffffff22"` | Background color of toolbar button when it's pressed
`ToolbarItemSelectedColor` | `"#ffffff44"` | Background color of toolbar button when it's selected
`GalleryBgColor` | `"#1E242900"` | Background color of gallery
`GalleryTextColor` | `"#dedede"` | Text color of gallery
`GalleryItemHoverColor` | `"#ffffff33"` | Background color of thumbnail when it's hovered
`GalleryItemActiveColor` | `"#ffffff22"` | Background color of thumbnail when it's pressed
`GalleryItemSelectedColor` | `"#ffffff44"` | Background color of thumbnail when it's selected
`MenuBgColor` | `"#1E2429"` | Background color of menu
`MenuBgHoverColor` | `"#ffffff15"` | Background color of menu item when it's hovered
`MenuTextColor` | `"#dedede"` | Text color of menu item
`MenuTextHoverColor` | `"#dedede"` | Text color of menu item when it's hovered
`NavigationButtonColor` | `"ff000015"` | Background color of the navigation arrow buttons



#### 🟢 Step 2.5 Section `ToolbarIcons`
Provides icons for toolbar. All icon files must be in SVG format for better scaling on high DPI screens.

Key name | Example value | Description
-- | -- | --
`ActualSize` | `"ActualSize.svg"` | The "Actual size" button
`AutoZoom` | `"AutoZoom.svg"` | The "Auto zoom" button
`Checkerboard` | `"Checkerboard.svg"` | The "Checkerboard" button
`ColorPicker` | `"ColorPicker.svg"` | The "Color picker" button
`Crop` | `"Crop.svg"` | The "Crop image" button
`Delete` | `"Delete.svg"` | The "Move to the Recycle Bin" button
`Edit` | `"Edit.svg"` | The "Edit" button
`Exit` | `"Exit.svg"` | The "Exit" button
`Export` | `"Export.svg"` | The "Export" button when the "Page navigation" tool is open
`FlipHorz` | `"FlipHorz.svg"` | The "Flip horizontal" button
`FlipVert` | `"FlipVert.svg"` | The "Flip vertical" button
`FullScreen` | `"FullScreen.svg"` | The "Full screen" button
`Gallery` | `"Gallery.svg"` | The "Gallery" button
`LockZoom` | `"LockZoom.svg"` | The "Lock zoom ratio" button
`MainMenu` | `"MainMenu.svg"` | The "Main menu" button
`OpenFile` | `"OpenFile.svg"` | The "Open file" button
`Pause` | `"Pause.svg"` | The "Pause" button when the "Page navigation" tool is open
`Play` | `"Play.svg"` | The "Play" button when the "Page navigation" tool is open
`Print` | `"Print.svg"` | The "Print" button
`Refresh` | `"Refresh.svg"` | The "Refresh" button
`RotateLeft` | `"RotateLeft.svg"` | The "Rotate left" button
`RotateRight` | `"RotateRight.svg"` | The "Rotate right" button
`Save` | `"Save.svg"` | The "Save image" button
`ScaleToFill` | `"ScaleToFill.svg"` | The "Scale to fill" button
`ScaleToFit` | `"ScaleToFit.svg"` | The "Scale to fit" button
`ScaleToHeight` | `"ScaleToHeight.svg"` | The "Scale to height" button
`ScaleToWidth` | `"ScaleToWidth.svg"` | The "Scale to width" button
`Slideshow` | `"Slideshow.svg"` | The "Slideshow" button
`ViewFirstImage` | `"ViewFirstImage.svg"` | The "View the first frame" button when the "Page navigation" tool is open
`ViewLastImage` | `"ViewLastImage.svg"` | The "View the last frame" button when the "Page navigation" tool is open
`ViewNextImage` | `"ViewNextImage.svg"` | The "View next image" button
`ViewPreviousImage` | `"ViewPreviousImage.svg"` | The "View previous image" button
`WindowFit` | `"WindowFit.svg"` | The "Window fit" button
`ZoomIn` | `"ZoomIn.svg"` | The "Zoom in" button
`ZoomOut` | `"ZoomOut.svg"` | The "Zoom out" button


### 🔵 Step 3. Add icons and image files
### 🔵 Step 4. Add preview image file for your theme (step 2.3)
### 🔵 Step 5. Pack your theme
- Rename your theme folder to match to the naming convention. Example: `Moon-light.james-black.igtheme`
- Compress the whole theme folder as `zip` file
- Change the `.zip` extension to `.igtheme`

### 🔵 Step 6. Share your theme
After creating a nice theme, don't forget sharing it to other people. You can
- Create [an issue here](https://github.com/ImageGlass/theme/issues), and attach your awesome theme; or
- Send your theme pack (`.igtheme`) to `phap@imageglass.org` email



## 💖 Support this project
ImageGlass stands as an open-source, ad-free photo viewer, yet its development and upkeep demand resources. Your financial backing not only sustains this project but also fuels my motivation for crafting future releases.

Should you opt for [GitHub Sponsor](https://github.com/sponsors/d2phap) or [Patreon](https://www.patreon.com/d2phap), be sure to explore the tier-specific benefits on offer.
Your support is greatly appreciated!

<a href="https://github.com/sponsors/d2phap" target="_blank" title="Become a sponsor">
<img src="https://img.shields.io/badge/Github-@d2phap-24292e.svg?maxAge=3600" height="30" alt="Become a sponsor">
</a>

<a href="https://www.patreon.com/d2phap" target="_blank" title="Become a patron">
<img src="https://img.shields.io/badge/Patreon-@d2phap%20-e85b46.svg?maxAge=3600" height="30" alt="Become a patron">
</a>

<a href="https://donorbox.org/imageglass" target="_blank" title="Wire transfer">
<img src="https://img.shields.io/badge/DonorBox-@imageglass%20-005384.svg?maxAge=3600" height="30" alt="Wire transfer">
</a>

<a href="https://www.paypal.me/d2phap" target="_blank" title="Buy me a beer?">
<img src="https://img.shields.io/badge/PayPal-Donate%20$10%20-0070ba.svg?maxAge=3600" height="30" alt="Buy me a beer?">
</a>


### ❤
Thank you!

