# Website screenshots

The 10 images referenced from `../index.html` (`01-calculator-main.png` …
`10-settings.png`) are produced by the automated tour in
`../../ui/screenshots/capture-screenshots.ps1`.

## How to populate this folder

```powershell
# 1. Run the tour for the webpage output format
cd ../../ui/screenshots
.\capture-screenshots.ps1 -Formats webpage -Locales en -Themes light

# 2. Copy webpage-sized PNGs into this folder
Copy-Item out\webpage\*.png ..\..\website\screenshots\
```

The tour stop numbers in `../../ui/screenshots/config/tour.json` align
1:1 with the filenames the gallery markup expects.

## Expected files

| File                              | Tour stop                |
|-----------------------------------|--------------------------|
| `01-calculator-main.png`          | Calculator (empty)       |
| `02-calculator-result.png`        | Calculator with result   |
| `03-calculator-playing.png`       | Calculator mid-playback  |
| `04-big-calculator.png`           | Big Calculator (24 keys) |
| `05-big-calculator-expression.png`| Big Calc with expression |
| `06-scales.png`                   | Scales screen            |
| `07-octaves.png`                  | Octaves screen           |
| `08-instruments.png`              | Instruments screen       |
| `09-saved.png`                    | Saved Calculations       |
| `10-settings.png`                 | Settings                 |

Each file should be a PNG at the webpage format size defined in
`tour.json` (1080 × 2160 by default, JPEG-quality compression).
