I made this to convert a large number of epub comics I had since epub doesn't work super well for comics.
This is made for my e-ink tablet, the supernote manta in mind. It will have the cover page as vertical 
and the other pages as if you were actually reading a comic, so a side-by-side, 2-page view. 

It works by copying the epub to a hidden folder, changing the file extension to zip, unzipping it, finding
the "images" folder, paste the pages together using imagemagick, then put all the files together in a folder,
finally zipping that folder into cbz format.

It doesn't work every time yet, but I will be making modifications in the future to cover more layouts within
the epubs

epub2cbz [-i jumbled_mode] [-j Japan_mode] [-d directory_mode] [file.epub | directory]
