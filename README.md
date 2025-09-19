### Background
I made this to convert a large number of epub comics I had since epub doesn't work super well for comics.
This is made for my e-ink tablet, the supernote manta in mind. It will have the cover page as vertical 
and the other pages as if you were actually reading a comic, so a side-by-side, 2-page view. 

It works by copying the epub to a hidden folder, changing the file extension to zip, unzipping it, finding
the "images" folder, paste the pages together using imagemagick, then put all the files together in a folder,
finally zipping that folder into cbz format.

It doesn't work every time yet, but I will be making modifications in the future to cover more layouts within
the epubs

### How To Use

epub2cbz [-i jumbled_mode] [-j Japan_mode] [-d directory_mode] [file.epub | directory]

-i jumbled_mode   -- This is for when the images are out of order. This option invokes imageRenamer and checks through 
                     html files. I've only needed it once so it only works in one scenario. For now.

-j Japan_mode     -- This reverses the images for reading right-to-left. It adds an extra cover at the end then
                     reverses the order of the images. This way you can read from the last page and swipe right 
                     instead of left.

-d directory_mode -- This just specifies the input is a directory name (use . for current directory) rather than a
                     single epub file and it will convert all epub files in that directory.

-c cover          -- This allows you to enter the path of an alternate cover. It only works on non-shuffled files as of now
