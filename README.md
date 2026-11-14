# AVA

A rebuild of the intro of [VIV](https://vivmgmt.com) (Awwwards Site of the Day, Nov 6 2026) with zero JavaScript of my own.
Every animation on the page is a class name from [Tweenwind](https://tweenwind.dimaac.com), my free library that turns
`gs-` classes into GSAP animations.

**Live demo:** https://dimaac.com/projects/ava
**Tutorial:** coming with the video
**Tweenwind:** https://tweenwind.dimaac.com ([npm](https://www.npmjs.com/package/tweenwind), [GitHub](https://github.com/Hank-D-Tank/tweenwind))

## How it works

The only script on the page is Tweenwind, which loads GSAP for you:

```html
<script src="https://cdn.jsdelivr.net/npm/tweenwind@0.2.0"></script>
```

- **The intro** is a few `load:` classes: the photos fade in one after another (`load:gs-target-[.photo] load:gs-fade load:gs-stagger-0.04`),
  the wall settles from `load:gs-from-[scale:1.3,y:5vh,transformOrigin:center_top]` and the logo is two SVGs that wipe in from
  opposite sides (`load:gs-reveal-left`, `load:gs-reveal-right`).
- **The breathing loop:** each column is a `load:gs-timeline load:gs-repeat` with a 5.48 s wait. Its top two tiles move down 70 px
  and back (`gs-to-[y:70] gs-repeat-1 gs-yoyo`) while their photos fade to a colour block and back.
- **The photo swap** hides in that fade: a second photo with its own `load:` loop switches on or off in 0.1 s every 7.6 s while the
  photos are faded out, and a tint layer fades the colour block to the new photo's colour.
- **The mouse pan** is one class on the gallery: `gs-pan-x-15vw`.
- **Hover and smooth scroll:** `gs-group` with `group-hover:gs-to-[rotate:90]` spins the plus icons, `gs-smooth` gives the page smooth scrolling.

Open `index.html` in any modern browser. Everything is in that one file.

## Credits

- Design and motion inspired by [VIV](https://vivmgmt.com) by Sam Dallyn, Awwwards Site of the Day. The brand, logo, names and photos here
  are placeholders; none of VIV's code or images are used.
- Photos from [Lummi](https://www.lummi.ai) (free licence), loaded from their CDN:
- "Red Confidence" by Pablo Stanley - https://www.lummi.ai/photo/QmYgE6KegbFArqqpY4h1wkx9UYJnpteYLcg7rm1f7ms71W
- "Modern Portrait" by Benginur Hajjaj - https://www.lummi.ai/photo/QmZeZFPNuSN6xmLJwbDmH1HzodLHauBhiTtwGgEiJmy1Ag
- "Woman in Orange Outfit Against Orange Background" by West Kast - https://www.lummi.ai/photo/Qma6LpshvmEjhMZ5QrwN82LNJ1SKQjdwM6gc1t5FDwyHDW
- "Retro Blue Portrait" by West Kast - https://www.lummi.ai/photo/QmTFPvWYUET5xyYivUdQYLdmbZYSWrrU2C6zowsmTR9U5U
- "Joyful Portraiture" by rena - https://www.lummi.ai/photo/QmSfeyr8U2EmTTwmcK8gbZdXyKhuRYqUPzBPpPmTXoUnqm
- "Fashion Portrait" by Amino - https://www.lummi.ai/photo/QmNWg3UTyEcMRJwVU1va8u4KSS9sqDjDGfkhTB9rEaRc4X
- "Elegant Pink Portrait" by Semihan Dosunmu - https://www.lummi.ai/photo/QmcgiAnbLEeZM9grSYoS6UDTJUdcDBejWBep3RZB9srP1a
- "Portrait of Young Woman" by West Kast - https://www.lummi.ai/photo/QmXgnDznSuiB7t7mqfvHmfg9sSTj6B1GfqWZxLo8LJdJHk
- "Confident Woman Against Pastel Backdrop" by berol - https://www.lummi.ai/photo/QmbMcWJ7Jh5H5tSrChjbhBrnSR1KuVEL4N7N5iG5VUChAo
- "Modern Fashion Portrait" by Semihan Dosunmu - https://www.lummi.ai/photo/QmSeYXsLN4iAPH3LfcVWnW5ZQLoiR4bKvtSyyV5XcJKjne
- "Modern Green Fashion" by Clemara Studio - https://www.lummi.ai/photo/QmcoELVDuJSB9T6pCoDegq945cJLsyivZmAo34maycH3pT
- "Vibrant Portrait" by Amino - https://www.lummi.ai/photo/QmSRj4czYp8w5C9TG9sCHvjbubLC9gd32FBWyfb3oGogJs
- "Confident Portrait" by West Kast - https://www.lummi.ai/photo/QmeEyhvxhYyLQiRnomGsJzMznuS4UEPE16mQtbDMczzGwb
- "Elegant Woman Portrait" by Shaun Duval - https://www.lummi.ai/photo/QmYXEmKvgYSTQ8wmk484jtPwgBBW4rvCmPrQPJe1JA84Nr
- "Dreamy Artistic Portrait" by Steph Meade - https://www.lummi.ai/photo/QmVFLR7i5PbXAGpWnrFHyLMQoKFdJj4Yd6MytYJ5sVWHzc
- "Dynamic Fashion Motion" by SHIHO - https://www.lummi.ai/photo/QmUYRevMXmZtnV9WcPsxB9iSZMcqUhxVGKw7BjNnH2AjKZ
- "Elegant Floral Bouquet" by Amino - https://www.lummi.ai/photo/QmS7T6Q2SNubT5KWc3zd7WQyo3sxeUw6fCNv917FpUhdqB
- "Geometric Balance in Blue and Orange" by Pablo Stanley - https://www.lummi.ai/photo/QmVEDNkUDQ5dTn6twRF3og6StHv1KydeFuKqVgZX7P98HS
- "Stylish Two-Tone Handbag" by Pablo Stanley - https://www.lummi.ai/photo/QmUvKjnRebG64HymDabfVz3WWz3L1gFPzEAjuGgpYoPbpp
- "Serene Desert Elegance" by Benginur Hajjaj - https://www.lummi.ai/photo/QmdYUdk7Ne6k5cfaQ4GsCtta9DicoEPMnQSNw1s4ekzDzw
- "Fashionable Orange Backdrop" by Amino - https://www.lummi.ai/photo/Qmb96RL4n1HJx8oKNXDZRvSBxKaAcCmbe4zqgmPcY3WN3y
- "Stylish Green Ensemble" by Semihan Dosunmu - https://www.lummi.ai/photo/Qmc6xBbvbmfu2HhVErV4HFrgnmJoGnxK7oCQgJrJa1rAw7
- "Contemplative Portrait Against Red Backdrop" by Pablo Stanley - https://www.lummi.ai/photo/QmTMAcuLRyhUxPbA5omP4og4GkXN6xv2ZLfdPZ2p71rvX4
- "Artistic Portrait of Man" by stacy 🪩🐉 - https://www.lummi.ai/photo/Qmf7uPGt3BUom7E2ftMWe1eLEimYqJzYWKHqWwBKyahnig
- "Monochromatic Purple Style" by LilacBlonde - https://www.lummi.ai/photo/QmNmVUuyRfC4uQw2MRymE1fZ3KgcbVk929aZBhsdhPxLHy
- Font: [Inter Tight](https://fonts.google.com/specimen/Inter+Tight) (SIL OFL).
