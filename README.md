# dcraw-json
I added a new option to dcraw, `-J`, to output exif metadata in JSON format. 
Not all of the metadata is printed, only the tags that another project of mine needs. Primitive data types
are in favor over strings, for example: `shutterSpeed: 0.001250` instead of `shutterSpeed: "1/800 sec"`.

I did code in the other tags but they're commented out (and not really tested). But as a bonus GPS data is provided as 
latitude and longitude coordinates (if available).

`$ ./dcraw -i -v -J /home/andy/Pictures/australia.jpg`

```json
{
	"filename": "/home/andy/Pictures/australia.jpg",
	"timestamp": 1160559472, 
	"camera": {
		"make": "Minolta",
		"model": "DiMAGE A2"
	},
	"isoSpeed": 100,
	"shutterSpeed": 0.001250,
	"aperture": 7.1,
	"focalLength": 33.3,
	"thumbnail": {
		"width": 160,
		"height": 122
	},
	"fullImage": {
		"width": 1024,
		"height": 768
	},
	"gps": {
		"latitude": -33.855833,
		"longitude": 151.219722
	}
}```
