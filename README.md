# The Automagical Icon Maker

A Photoshop template for generating pretty much every size of icon image you’ll reasonably need for web projects.

[Audrey Roy](https://github.com/audreyr) put together the [Favicon Cheat Sheet](https://github.com/audreyr/favicon-cheat-sheet) which I used as the jumping off point for this quick little tool.

## Why?

This just speeds up the generation of an assortment of icon sizes you might need for desktop, various mobile platforms, etc. I use it. I thought other people might find it useful too. 

## How?

I'm leveraging the [Generator](http://blogs.adobe.com/photoshopdotcom/2013/09/introducing-adobe-generator-for-photoshop-cc.html) functionality in Photoshop 14.1 and newer to make this dead simple. If you prefer to use *Save for Web..*, I’ve included slices in the template as well.

### How to get your artwork into the template
 
 1. Open `automagical-icon-maker.psd` in Photoshop.
 2. Edit the smart object in the layer named `favicon-152.png`
 3. Add your artwork to the smart object
 4. Save the smart object
 5. Your artwork should now be populated into all of the sizes in the template
 
### Generating the image files

Select `File > Generate > Image Assets`. Your images should now be now available in a folder named `automagical-icon-maker-assets`. 

*This uses the Generator functionality built into Photoshop 14.1 and up. With this enabled, new icon files are automatically created any time you make additional changes to the artwork. Neat!*

Note: You can still just export the image files with Save for Web..., slices have already been defined.

### Making an ICO file

Creating a `.ico` file in addition to the png files we‘re already generating requires an addtional couple of steps. 

We already have our 32 x 32 and 16 x 16 png files. Use the tool of your choice to slap both of these files into a single ico file. Most recently, I’m liking [Icon Slate](http://www.kodlian.com/apps/icon-slate) (mac) to do this. It’s a quick and simple little utility that‘ll save you time and hassle. 

## The HTML

These are selected portions taken from Audrey Roy‘s [Favicon Cheat Sheet](https://github.com/audreyr/favicon-cheat-sheet) that pertain to the image sizes we‘re generating. I decided to only go medium-crazy with the sizes I've included. Audrey is going for obsessively exhaustive. *Bravo, Audrey!* (You should check that sucker out, regardless. Good stuff there.)

For the main favicon itself, it's best for cross-browser compatibility not to use any HTML. Just name the file favicon.ico and place it in the root of your domain.[1][1],[2][2]

 1. Touch icon for iOS 2.0+ and Android 2.1+:  

    `
    <link rel="apple-touch-icon-precomposed" href="path/to/favicon-152.png">`
   
 2. IE 10 Metro tile icon (Metro equivalent of apple-touch-icon):

    `
    <meta name="msapplication-TileColor" content="#FFFFFF">   
    <meta name="msapplication-TileImage" content="/path/to/favicon-144.png">`

 3. Largest to smallest apple-touch-icons [3][3] : 

```<!-- For iPad with high-resolution Retina display running iOS ≥ 7: -->  
    <link rel="apple-touch-icon-precomposed" sizes="152x152" href="/path/to/favicon-152.png">  
    
    <!-- For iPad with high-resolution Retina display running iOS ≤ 6: -->  
    <link rel="apple-touch-icon-precomposed" sizes="144x144" href="/path/to/favicon-144.png">  
    
    <!-- For iPhone with high-resolution Retina display running iOS ≥ 7: -->  
    <link rel="apple-touch-icon-precomposed" sizes="120x120" href="/path/to/favicon-120.png">  
    
    <!-- For iPhone with high-resolution Retina display running iOS ≤ 6: -->  
    <link rel="apple-touch-icon-precomposed" sizes="114x114" href="/path/to/favicon-114.png">  
    
    <!-- For first- and second-generation iPad: -->  
    <link rel="apple-touch-icon-precomposed" sizes="72x72" href="/path/to/favicon-72.png">  
    
    <!-- For non-Retina iPhone, iPod Touch, and Android 2.1+ devices: -->  
    <link rel="apple-touch-icon-precomposed" href="/path/to/favicon-57.png">  ```

4. Favicons targeted to any additional png sizes that you add that aren't covered above:
    
    `
    <link rel="icon" href="/path/to/favicon-32.png" sizes="32x32">`  


## The Images

============= =============== =======================================================================
Sizes         Name            Purpose
============= =============== =======================================================================
16x16 & 32x32 favicon.ico     Default required by IE. Chrome and Safari may pick ico over png, sadly.
============= =============== =======================================================================

More about favicon.ico below. Yes, it‘s one file with multiple sizes.

======= =============== =======================================================================
Size    Name            Purpose
======= =============== =======================================================================
152x152 favicon-152.png General use iOS/Android icon, auto-downscaled by devices.
======= =============== =======================================================================

But keep in mind that icons with complex detail often don't downscale well.
Often you have to tweak subtle design details for smaller sizes.

======= =============== =======================================================================
Size    Name            Purpose
======= =============== =======================================================================
32x32   favicon-32.png  Certain old but not too old Chrome versions mishandle ico
57x57   favicon-57.png  Standard iOS home screen (iPod Touch, iPhone first generation to 3G)
72x72   favicon-72.png  iPad home screen icon
120x120 favicon-120.png iPhone retina touch icon (Change for iOS 7: up from 114x114)
144x144 favicon-144.png IE10 Metro tile for pinned site
152x152 favicon-152.png iPad retina touch icon (Change for iOS 7: up from 144x144)
======= =============== =======================================================================

## ICO File

An .ico file is a container for multiple .bmp or .png icons of different sizes.
In favicon.ico, create at least these:

======= =======================================================================
Size    Purpose
======= =======================================================================
16x16   IE9 address bar, Pinned site Jump List/Toolbar/Overlay
32x32   New tab page in IE, taskbar button in Win 7+, Safari Read Later sidebar
======= =======================================================================

Create your .ico out of optimized .png files.

## References

[1]: http://mathiasbynens.be/notes/rel-shortcut-icon
[2]: http://www.w3.org/html/wg/drafts/html/CR/links.html#rel-icon
[3]: Adapted from http://mathiasbynens.be/notes/touch-icons
