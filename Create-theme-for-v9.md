# ImageGlass 9 Theme Pack
Customize the appearance of ImageGlass by creating your own theme pack. An ImageGlass theme pack is an archive file with a `.igtheme` extension that can be opened with any archive viewer, such as WinRar or 7Zip, or simply change its extension to `.zip` and open it with File Explorer on Windows.

This documentation guides you through creating a theme pack for ImageGlass version 9 or above.

## Theme Pack Structure
A theme pack folder should contain the following:
- 1 `igtheme.json` file: This essential file stores all theme settings and enables ImageGlass to recognize the theme pack.
- 1 theme preview image file: ImageGlass displays this image file as a theme preview in the Settings dialog.
- SVG icon files: These are for toolbar icons, the app logo, and other visual elements.

All of these files should be placed in a folder named `THEME_FOLDER`. The structure should resemble the following:
```
THEME_PACK.igtheme
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
- `theme-name` is the name of the theme, separated by hyphens `-`.
- `author-name` is the name of the author, separated by hyphens `-`.

For example: `Kobe.Duong-Dieu-Phap`, `2017-Light-Gray.Duong-Dieu-Phap`.


`THEME_PACK.igtheme` follows a similar convention, with the extension:
```
<theme-name>.<author-name>.igtheme
```
For example: `Kobe.Duong-Dieu-Phap.igtheme`, `2017-Light-Gray.Duong-Dieu-Phap.igtheme`.


## Create a Theme Pack for ImageGlass 9
### Step 1. Create the theme pack folder structure
### Step 2. Create the `igtheme.json` file
This is the most crucial file in the theme pack, providing all the necessary SVG icon files to the ImageGlass app, along with other theme information. The structure of this file is in JSON format, detailed as follows:
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

::: { .box .d-flex }
💡 For a complete example of `igtheme.json` file, please refer to [dark/Green-Gradient.Duong-Dieu-Phap/igtheme.json](https://github.com/ImageGlass/Theme/blob/main/themes/dark/Green-Gradient.Duong-Dieu-Phap/igtheme.json).
:::

#### 🟢 Step 2.1: Section `_Metadata`
Provides the metadata of the ImageGlass theme pack. Do not alter this section.

Key name | Value | Description
-- | -- | --
`Version` | `"9.0"` | Version of the configuration file (do not change it)
`Description` | `"ImageGlass theme configuration file"` | A constant description (do not change it)


#### 🟢 Step 2.2: Section `Info`
Provides basic information of your theme pack.

Key name | Example value | Description
-- | -- | --
`Name` | `"Moon light"` | The name of your theme, visible in the ImageGlass theme list
`Version` | `"1.0"` | The version number of your theme
`Description` | `"A Moon light dark theme for ImageGlass"` | A short description of your theme
`Author` | `"Duong Dieu Phap"` | The author who created this theme pack (optional)
`Email` | `"phap@example.com"` | The author's contact email (optional)
`Website` | `"https://example.com"` | The author's website (optional)



#### 🟢 Step 2.3: Section `Settings`
Provides general settings of your theme pack.

Key name | Example value | Description
-- | -- | --
`IsDarkMode` | `true` | Theme pack color mode; the default value is `true`
`NavButtonLeft` | `"ViewPreviousImage.svg"` | The left arrow navigation button SVG icon
`NavButtonRight` | `"ViewNextImage.svg"` | The right arrow navigation button SVG icon
`AppLogo` | `"logo.svg"` | The logo of ImageGlass, displayed on the title bar of all windows
`PreviewImage` | `"preview.webp"` | The preview image of the theme pack; recommended formats include WebP and JPG



#### 🟢 Step 2.4: Section `Colors`
Defines the color scheme of ImageGlass. All colors should be in HEX code (web format), including alpha values.

Example: `#fff`, `#fffa`, `ffffff`, `ffffffaa`, etc. ImageGlass also supports using the system accent color for your theme pack:
- You can use `"accent"` as a color value
- You can adjust the alpha value of the accent color using this syntax: `<accent>:<alpha>`. The `alpha` value should be from `0` to `255`. Example: `"accent:70"`.

Key name | Example value | Description
-- | -- | --
`BgColor` | `"#151b1f00"` | Background color of the viewer
`TextColor` | `"#d3d3d3"` | Text color of the viewer
`ToolbarBgColor` | `"#1E242900"` | Background color of the toolbar
`ToolbarTextColor` | `"#dedede"` | Text color of toolbar buttons
`ToolbarItemHoverColor` | `"#ffffff33"` |Background color of toolbar buttons when hovered
`ToolbarItemActiveColor` | `"#ffffff22"` |Background color of toolbar buttons when pressed
`ToolbarItemSelectedColor` | `"#ffffff44"` |Background color of toolbar buttons when selected
`GalleryBgColor` | `"#1E242900"` | Background color of the gallery
`GalleryTextColor` | `"#dedede"` | Text color of gallery thumbnails
`GalleryItemHoverColor` | `"#ffffff33"` | Background color of gallery thumbnails when hovered
`GalleryItemActiveColor` | `"#ffffff22"` | Background color of gallery thumbnails when pressed
`GalleryItemSelectedColor` | `"#ffffff44"` | Background color of gallery thumbnails when selected
`MenuBgColor` | `"#1E2429"` | Background color of the menu
`MenuBgHoverColor` | `"#ffffff15"` | Background color of menu items when hovered
`MenuTextColor` | `"#dedede"` | Text color of menu items
`MenuTextHoverColor` | `"#dedede"` | Text color of menu item when hovered
`NavigationButtonColor` | `"ff000015"` | Background color of the navigation arrow buttons


#### 🟢 Step 2.5: Section `ToolbarIcons`
Provides icons for the toolbar. All icon files should be in SVG format for better scaling on high DPI screens.

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


### Step 3. Copy Icon and Image Files to The Theme Folder
### Step 4. Add a Theme Preview Image File as Specified in Step 2.3
### Step 5. Pack Your Theme
Rename your theme folder to match the naming convention, compress the whole theme folder as a `.zip` file, and change the extension to `.igtheme`.

Example: `Moon-light.Duong-Dieu-Phap.igtheme`.

### Step 6. Share Your Theme
After creating an impressive theme, don't forget to share it with others. You can:
- Open [an issue here](https://github.com/ImageGlass/theme/issues), and attach your fantastic theme;

