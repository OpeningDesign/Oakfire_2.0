# Illuminance plan

The two main lighting requirements are:

 1. No artificial light spillage measured at and beyond the property boundary
    should be >=0.5fc.
 2. The average illuminance across the parking lot should be >=2fc.

The product used to represent the perimeter wall luminaire is available
[here](https://teronlighting.com/products/ginty-led/).

The product used to represent the parking lights is available
[here](http://www.cooperindustries.com/content/public/en/lighting/products/area_site_lighting/_808353.html).
The 4 square option was chosen. Parking lights are positioned just under 25' in
the air.

## How to run

```
$ rad scene.rif
$ ximage scene_v1.hdr # View results
$ falsecolor -ip scene_v1.hdr -cl -l fc -s a -m 16.629505759940542 > false.hdr
$ ximage false.hdr # see contours to verify requirement 1
$ pcomb -o -s 0.0929 scene_v1.hdr > scene_v1_fc.hdr # Convert to fc unit
$ ximage scene_v1_fc.hdr # use `l` to verify requirement 2
$ gimp false-overlay.xcf # create overlay
```

The source file `scene.blend` provides the `scene.obj` export.
