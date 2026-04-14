# ASCIIfy
1. Executive Summary
ASCIIfy is a zero-dependency, browser-based ASCII art generator that converts any image into ASCII art with real-time controls, multiple color modes, image processing effects, and export in three formats. It runs entirely client-side — no server, no backend, no cost to scale.
Goal: Be the best ASCII art tool on the internet.
Target Users: Developers, designers, digital artists, hackers, retro enthusiasts.

2. Problem Statement
Existing ASCII art generators are:

Outdated (Flash-era, no mobile support)
Low control (one slider, one export)
No color support
Ugly UX — you wouldn't share a screenshot of the tool itself

ASCIIfy solves all of this.

3. Feature Set (v1.0)
3.1 Input
FeatureDescriptionDrag & drop uploadDrag any image file onto the drop zoneClick to browseFile picker for PNG, JPG, GIF, WebP, SVGPaste from clipboardCmd/Ctrl+V pastes images directlyLive preview thumbnailShows original image after load
3.2 Image Controls
ControlRangeDescriptionWidth (cols)30–250Character grid widthBrightness-80 to +80Brighten/darken before conversionContrast0.5×–3×Amplify tonal rangeEdge Sharpen0–5Pre-sharpen before conversionBlur0–5pxSmooth noisy images
3.3 Character Sets
NameCharacters UsedDetailed@%#*+=-:.Simple@#+-.Blocks█▓▒░ (Unicode)Dots●◉◎○◌ (Unicode)Binary1, 0Braille⣿⣷⣯ (Unicode Braille)MatrixJapanese katakanaEmojiMoon phase emoji for grayscale
3.4 Color Modes
ModeBehaviorMonoSingle color — user selects from 7 presetsFull ColorEach character gets the original pixel's RGBInvertInverted luminance mappingSepiaWarm tinted monochromeNeonCycling neon rainbow colorsMatrixGreen phosphor style
3.5 Image Processing Effects
EffectTypeDescriptionFlip HorizontalTransformMirror X-axisFlip VerticalTransformMirror Y-axisRotate 90°TransformRotate image before ASCII conversionDitherAlgoFloyd-Steinberg dithering for crisp B&WEdge DetectAlgoSobel operator — outlines only
3.6 Border Frames
Single, Double, Heavy, Rounded (box-drawing chars), Dotted, or None.
3.7 Export
FormatDescription.txtPlain text file, preserves chars.pngRendered dark-bg image at pixel-perfect scale.svgScalable vector, color-awareClipboardCopy entire ASCII text
3.8 Gallery & History

History: Last 20 renders auto-saved in memory. View, restore.
Gallery: Name and manually save pieces. Persist in memory during session.

3.9 UI/UX

Dark/Light theme toggle
Zoom control (+/- buttons, keyboard shortcuts)
Stats bar: cols × rows × total chars
Toast notifications for all actions
Keyboard shortcuts: Cmd+S = PNG, Cmd+C = copy, +/- = zoom


4. Technical Architecture
ASCIIfy/
├── index.html         # Entire app (HTML + CSS + JS)
├── vercel.json        # Vercel static deployment config
└── README.md          # Docs
Stack: Vanilla HTML/CSS/JS. Zero dependencies. Zero npm. Zero build step.
Rendering: HTML5 Canvas for pixel sampling.
Algorithms: Floyd-Steinberg dithering, Sobel edge detection, in-browser.
Deployment: Vercel static hosting — deploy in 30 seconds.

![Screenshot_14-4-2026_115541_vercel com](https://github.com/user-attachments/assets/b2244fae-9763-4d4b-b289-134d633a5a8a)
![Screenshot_14-4-2026_115541_vercel com](https://github.com/user-attachments/assets/8d841636-138f-4d39-82ef-3d624b3dcf3d)
<img width="740" height="625" alt="ascii" src="https://github.com/user-attachments/assets/3aa99f16-6b22-4a66-bdca-9d7ae5c15db1" />


