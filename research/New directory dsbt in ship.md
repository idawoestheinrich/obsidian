We have a new directory for our testbeam data and pictures as well as simulation and analysis, if people are interested `/eos/experiment/ship/dsbt`

You will find the all the testbeam data in `/eos/experiment/ship/dsbt/testbeam/testbeam_<year of the testbeam>-<month of the testbeam>` 

That means for the last testbeam :
`/eos/experiment/ship/dsbt/testbeam/testbeam_2025-11` 
There are folders:
- `testbeam_cell_A` with data from Cell A
- `testbeam_cell_A_FastIC` with data from Cell A readout with FastIC
- `testbeam_cell_L` with data from Cell L
- `pictures` where pictures and videos can be uploaded 
- `documentation` where all kinds of documentation can be uploaded (Log book, other notes)
##### Pictures and videos
I did not manage to divide the pictures folder into subfolder except for one subfolder `group_pictures` . Please upload group pictures to that subfolders.
Except for that it makes sense to name the pictures after the time when they were taken. 
##### Upload pictures and videos manual
-  Please name the pictures in the following way `2025-<month>-<day>_<hour>-<minute>.png`
	- You can also use other common picture formats 
	- To save work I just put all pictures in one folder and than ask ChatGPT to write a small script to covert my *.HEIC* pictures into *.png* 
	- For me that looked like this, but you can just generate:
		###### Install exiftool (if you don’t have it)
		`brew install exiftool`
		###### Convert & rename all HEICs in a folder
		Run this in the directory with your `.HEIC` files:
```shell
for f in *.HEIC; do
    # Extract EXIF date as YYYY-MM-DD_HH-MM-SS
    dt=$(exiftool -DateTimeOriginal -d "%Y-%m-%d_%H-%M-%S" -s3 "$f")

    # Fallback if no EXIF date exists
    if [ -z "$dt" ]; then
        dt=$(date -r "$(stat -f %m "$f")" "+%Y-%m-%d_%H-%M-%S")
    fi

    # Create output name
    out="${dt}.png"

    # Convert
    sips -s format png "$f" --out "$out"

    echo "Created: $out"
done
```
- If you than want to upload these pictures and movies to the directory simply run from the folder where your pictures are
`scp - r * <username>@lxplus.cern.ch:/eos/experiment/ship/dsbt/testbeam/testbeam_2025-11/pictures`
- enter your password and the 2nd factor
- Please upload group pictures to `/eos/experiment/ship/dsbt/testbeam/testbeam_2025-11/pictures/group_pictures`
- Please upload documentation to `/eos/experiment/ship/dsbt/testbeam/testbeam_2025-11/documentation`