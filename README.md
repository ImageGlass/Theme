# ImageGlass theme packs
The up-to-date theme packs for [ImageGlass](https://imageglass.org/)

## Theme pack folder structure
A theme pack contains:
- 1 `config.xml` file
- 1 preview image file
- And SVG icon files

All of these files should be placed in a folder.

```
THEME_NAME
|-- config.xml
|-- preview image file
|-- SVG icon files...
```

## How to create a new theme pack
### 1. Create theme pack folder structure
### 2. Create `config.xml` file
This is the most important file of the theme, it provides all the SVG icon files to ImageGlass app and other information of your theme.
You can see full `config.xml` example at https://github.com/ImageGlass/theme/blob/master/themes/dark/2017_dark/config.xml

There are 3 sections in `<Theme>` element:

```xml
<ImageGlass>
  <Theme>
    <Info />
    <main />
    <toolbar_icon />
  </Theme>
</ImageGlass>
```

#### 2.1 `<Info />` element
Provides general information of your theme packs, all options are:

Key | Example | Description
-- | -- | --
name | `name="2017 (Dark)"` | Name of your theme which people will see it in ImageGlass theme list.
description | `description="Modern ImageGlass theme (Dark)"` | A short description of your theme.
version | `version="1.0"` | The version number of your theme.
author | `author="Duong Dieu Phap"` | The author name who creates this theme pack (optional).
email | `email="phap@imageglass.org"` | The contact email of the author (optional).
website | `website="https://imageglass.org"` | The website of the author (optional).
type | `type="ImageGlass Theme Configuration"` | 🚫 Just a constant (don't change it).
compatibility | `compatibility="5.0"` | The minimum ImageGlass version that this theme can work with.
preview | `preview="preview.png"` | The small preview image which people will have a glance on it. The size should be `253 x 100 px`.

Full example:
```xml
<Info name="2017 (Dark)"
    version="4.1"
    author="Dương Diệu Pháp"
    email="phap@imageglass.org"
    website="https://imageglass.org"
    description="Modern ImageGlass theme (Dark)"
    type="ImageGlass Theme Configuration"
    compatibility="5.0"
    preview="preview.png" />
```

#### 2.2 `<main />` element
Provides color scheme of ImageGlass. It should be either decimal color code or HEX code (no alpha value). All options are:

Key | Example | Description
-- | -- | --
topbarcolor | `topbarcolor="#3a3c3d"` | The color of toolbar.
bottombarcolor | `bottombarcolor="#3a3c3d"` | The color of thumbnail bar.
backcolor | `backcolor="#3a3c3d"` | The color of viewer area.
statuscolor | `statuscolor="#f0f0f0"` | The color of text, used in tool forms: Color picker, Page navigation, ...
menubackgroundcolor | `menubackgroundcolor="#484b4c"` | The background color of menu.
menutextcolor | `menutextcolor="#f0f0f0"` | The text color of menu.
topbar | `topbar="toolbar_bg.png"` | The background image file of the toolbar. This overrides the `topbarcolor` value. Invalid file ignored.
bottombar | `bottombar="thumb_bg.png"` | The background image file of the thumbnail. This overrides the `bottombarcolor` value. Invalid file ignored.

Full example:
```xml
<main topbar=""
    bottombar=""
    topbarcolor="#3a3c3d"
    bottombarcolor="#3a3c3d"
    backcolor="#3a3c3d"
    statuscolor="#f0f0f0"
    menubackgroundcolor="#484b4c"
    menutextcolor="#f0f0f0" />
```

#### 2.3 `<toolbar_icon />` element
Provides icons for toolbar. It's recommended to use SVG file format for better scaling on high DPI screens.
All options are:

Key | Example | Description
-- | -- | --
back | `back="ViewPreviousImage.svg"` | The Back navigation button.
next | `next="ViewNextImage.svg"` | The Next navigation button.
gofirst | `gofirst="GoToFirst.svg"` | The Go to first image button.
golast | `golast="GoToLast.svg"` | The Go to last image button.
 |  | 
leftrotate | `leftrotate="RotateLeft.svg"` | The Rotate left button.
rightrotate | `rightrotate="RotateRight.svg"` | The Rotate right button.
fliphorz | `fliphorz="FlipHorz.svg" ` | The Flip horizontal button.
flipvert | `flipvert="FlipVert.svg"` | The Flip vertical button.
crop | `crop="Crop.svg"` | The Cropping tool button.
colorpicker | `colorpicker="ColorPicker.svg"` | The Color picker tool button.
 |  | 
zoomin | `zoomin="ZoomIn.svg"` | The Zoom in button.
zoomout | `zoomout="ZoomOut.svg"` | The Zoom out button.
 |  | 
autozoom | `autozoom="AutoZoom.svg"` | The Auto zoom button.
zoomlock | `zoomlock="LockRatio.svg"` | The Lock zoom ratio button.
scaletowidth | `scaletowidth="ScaleToWidth.svg"` | The Scale to width button.
scaletoheight | `scaletoheight="ScaleToHeight.svg"` | The Scale to height button.
zoomtofit | `zoomtofit="ScaleToFit.svg"` | The Scale to fit button.
scaletofill | `scaletofill="ScaleToFill.svg"` | The Scale to fill button.
scaletofit | `scaletofit="ActualSize.svg"` | The Actual size button.
 |  | 
open | `open="OpenFile.svg"` | The Open file button.
refresh | `refresh="Refresh.svg"` | The Refest button.
gotoimage | `gotoimage="GoToImage.svg"` | The Go to button.
 |  | 
autosizewindow | `autosizewindow="AdjustWindowSize.svg"` | The Window fit button.
fullscreen | `fullscreen="FullScreen.svg"` | The FullScreen button.
slideshow | `slideshow="Slideshow.svg"` | The Slideshow button.
 |  | 
checkerboard | `checkerboard="Checkerboard.svg"` | The Checkerboard button.
thumbnail | `thumbnail="ThumbnailBar.svg"` | The Thumbnail bar button.
delete | `delete="delete.svg"` | The Move to recycle bin button.
print | `print="Print.svg"` | The Print button.
edit | `edit="Edit.svg"` | The Edit button.
convert | `convert="Convert.svg"` | The Save image as button.
 |  | 
menu | `menu="Menu.svg"` | The main menu button.












