## Overlay image

convert -composite -gravity center -geometry 4100x4000+30+750 background.png frontground.png final-file.png
-composite -gravity center = overlay frontground.png
-geometry 4100x4000+30+750 = 4100x4000 - size, +30+750 - alignment

## Change image colour

convert initial-file.png -fuzz 5% -fill '#newcolour' -opaque '#oldcolour' final-file.png
-fuzz 5%             = match 5% closest colours
-fill '#newcolour'   = change to the new colour
-opaque '#oldcolour' = match the old colour

## Make image transparent

convert initial-file.png -transparent '#colourtoremove' -fuzz 5% totoro-transparent.png
-transparent '#colourtoremove' = make colour #colourtoremove transparent
-fuzz 5%                       = match 5% closest colours