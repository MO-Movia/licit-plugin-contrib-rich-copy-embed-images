

# RichCopyEmbedImage Plugin For Licit

Plugin allows to encode the copied image for paste and export the current document.  

## Build  

### Commands
- npm install
- npm pack  

#### To use this in Licit

- npm install *mo-licit-rich-copy-embed-images-0.1.0.tgz*

####  To include plugin in Licit Component 

- import RichCopyEmbedImagePlugin 

- add RichCopyEmbedImagePlugin instance in licit's plugin array

```
import RichCopyEmbedImagePlugin from '@mo/licit-rich-copy-embed-images';  
const plugins = [new RichCopyEmbedImagePlugin()]

ReactDOM.render(<Licit docID={0} plugins={plugins}/>
```
#### How to use this plugin in Licit Editor
This plugin is responsible for "Copy Special". The Copy Special is NOT a mode. If user select Copy Special, editor loads up the copy buffer with all base 64 images. It is only when I choose that command. Thus, when user select the command, the complete operation of switching all images that are linked into base 64 embedded images as you load up the data into the copy buffer. This also means that it doesn't need the plugin on the paste side. If user activate the Copy Special command and then go paste anywhere else, it will only have those base 64 images in the copy buffer to paste.

To choose Copy Special : Use **Ctrl+Alt+C**

To export the encoded document data, use the below options: 

 1. **Ctrl+Alt+E**,  converts the current copied selected image(s) to base64 in the document and shall auto download a JSON file in the name format 'licit-YYYYMMDDhhmmssSS'.
 2.  **Ctrl+Alt+Shift+E**,  converts all the images to base64 in the document

 