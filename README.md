🎏 ImageGlass theme packs
==
The up-to-date theme packs for [ImageGlass](https://imageglass.org/)

[![Website](https://img.shields.io/badge/www-imageglass.org-0099BC.svg?maxAge=3600)](https://imageglass.org)
[![GPL Licence](https://img.shields.io/badge/license-MIT-green.svg?maxAge=3600)](https://github.com/ImageGlass/theme/blob/master/LICENSE)


[![Total Downloads](https://img.shields.io/github/downloads/ImageGlass/theme/total?color=%233097B8&label=downloads&style=for-the-badge)](https://imageglass.org/themes)



## 📂 Theme pack folder structure
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

## 🎨 How to create a new theme pack?
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


### 3. Add icons and image files
### 4. Add preview image file for your theme (step 2.1)
### 5. Pack your theme
- Zip the whole theme folder as `.zip`.
- Change the `.zip` extension to `.igtheme`.

### 6. Share your theme
After creating a nice theme, don't forget sharing it to other people. You can
- Create [an issue here](https://github.com/ImageGlass/theme/issues), and attach your awesome theme; or
- Send your theme pack (`.igtheme`) to `phap@imageglass.org` email.




## Donation
ImageGlass is free and open source but developing it has taken thousands of hours of my time and a large part of my sanity. If you feel this little viewer useful to you, it would go a great way to ensuring that I can afford to take the time to continue to develop it.

Thanks for your gratitude and finance help!

<a href="https://www.paypal.me/d2phap" target="_blank" title="Buy me a beer?">
<img src="https://img.shields.io/badge/PayPal-Donate%20$10%20-009be1.svg?maxAge=3600" height="30" alt="Buy me a beer?">
</a>


<a href="https://github.com/sponsors/d2phap" target="_blank" title="Become a sponsor">
<img src="https://img.shields.io/badge/Github-github.com%2Fsponsor%2Fd2phap-E84646.svg?maxAge=3600" height="30" alt="Become a sponsor">
</a>



<img src="https://img.shields.io/badge/Bitcoin-Donate-f7931a.svg?maxAge=3600" height="30" alt="Bitcoin">

```
3Hp7QLP9Fxpb1s4CAcZFYR7NUgN1bR93Hy
```



<img src="https://img.shields.io/badge/Ethereum-Donate-131313.svg?maxAge=3600" height="30" alt="Ethereum">

```
0x6DDBd646586bebF7a97e022D615cbE789D39a965
```




### ❤
Thank you!
