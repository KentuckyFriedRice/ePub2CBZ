### Background
I made this to convert a large number of epub comics I had since epub doesn't work super well for comics.
This is made for my e-ink tablet, the supernote manta in mind. It will have the cover page as vertical 
and the other pages as if you were actually reading a comic, so a side-by-side, 2-page view. 

It works by copying the epub to a hidden folder, changing the file extension to zip, unzipping it, finding
the "images" folder, paste the pages together using imagemagick, then put all the files together in a folder,
finally zipping that folder into cbz format. The finished cbz file is saved in a folder named "converted."

### How To Use

**epub2cbz** [ **-i**  *jumbled_mode* ]  [ **-j**  *Japan_mode* ]  [ **-d**  *directory_mode* ]  [ ***file.epub*** | ***directory*** ]

**-i**  *jumbled_mode*   -- This is for when the images are out of order. This option invokes imageRenamer and checks through 
                     html files. I've only needed it once so it only works in one scenario. For now.

**-j**  *Japan_mode*     -- This reverses the images for reading right-to-left. It adds an extra cover at the end then
                     reverses the order of the images. This way you can read from the last page and swipe right 
                     instead of left.

**-d**  *directory_mode* -- This just specifies the input is a directory name (use . for current directory) rather than a
                     single epub file and it will convert all epub files in that directory.

**-c**  *cover*          -- This allows you to enter the path of an alternate cover. It only works on non-shuffled files as of now

### File Layout
| Script Name | Description |
-----|-----
| epub2cbz | This is the main script that takes in all the options and file/directory. This is its own file because it is what handles the difference between a single epub file and a directory. |
| epub2cbz_converter | This is script which does the conversion. It takes a single file and options. You can use it independently for a single file if you wanted. I chose to leave it for the convenience of using one command. |
| imageRenamer | This is the script that unshuffles images. It reads the html file of each page and copies the associated image file into a new directory named as the page number. It then uses this new directory to make the cbz file. |

### Known Problems
- If you do jumbled and Japan mode and also set a custom cover, the pictures get moved forward one. I'm sure it's a logic problem but I haven't had time to find the issue.
- I don't think it works with every epub comicbook. I just update the code as I need it.
- There might be some issue with filenames but I haven't been able to pinpoint when it happens.
- You have to hold Ctrl+C to cancel the process.
- If you cancel the process, the folder isn't automatically cleaned up.
