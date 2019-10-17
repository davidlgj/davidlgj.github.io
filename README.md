

ls knitcounterimg | xargs -L1 -I "{}" convert knitcounterimg/{} -sampling-factor 4:2:0 -strip -quality 85 -interlace JPEG -colorspace RGB -resize 1920 -unsharp 0.25x0.25+8+0.065 knitcounter/{}

  ls knitcounterimg | xargs -L1 -I "{}" convert knitcounterimg/{} -sampling-factor 4:2:0 -strip -quality 85 -interlace JPEG -colorspace RGB -resize 600 -unsharp 0.25x0.25+8+0.065 knitcounter/sm-{}
