# Push-Pull Encoder

<p align="center"><picture><source media="(prefers-color-scheme: dark)" srcset="docs/img/hero-dark.gif"><img src="docs/img/hero.gif" width="340" alt="Push-pull encoder: turn, push, pull"></picture></p>

A rotary encoder that also pushes and pulls, like the knobs on an Airbus FCU: turn to set a value, pull for selected, push for managed. It all fits in a 27 mm square housing.

Both boards come from one PCB design. The headers you fit decide which becomes the top and which the bottom, and the two stack face to face, so there's only one board design to order.

[Two versions](#two-versions) · [Parts and where to buy](#parts-and-where-to-buy) · [Ordering the PCB](#ordering-the-pcb) · [One PCB, two jobs](#one-pcb-two-jobs) · [How it works](#how-it-works) · [Files](#files)

## Two versions

<p align="center"><picture><source media="(prefers-color-scheme: dark)" srcset="docs/img/versions-dark.png"><img src="docs/img/versions.png" width="560" alt="The through-hole-button and SMD-button builds side by side"></picture></p>

Only the two push buttons differ. Everything else, encoder and headers included, is through-hole in both builds.

| | Through-hole buttons | SMD buttons |
|:--|:--|:--|
| Push buttons | SAMZO 2010751102 | Panasonic EVQ9P105M |
| Height | 35 mm housing | 30 mm housing, 5 mm shorter |
| Long pin header | 21 mm | 17 mm |
| Assembly instructions | **[Through-hole buttons](docs/through-hole-buttons.md)** | **[SMD buttons](docs/smd-buttons.md)** |
| Printable | [PDF, 3 pages](assembly-instructions-through-hole-buttons.pdf) | [PDF, 3 pages](assembly-instructions-SMD-buttons.pdf) |

The SMD buttons are lower, so the boards sit 15 mm apart instead of 20 mm and the whole stack is 5 mm shorter. The through-hole buttons are easier to solder.

## Parts and where to buy

| Qty | Part | Build | Buy |
|--:|:--|:--:|:--|
| 2 | PCB, 20 × 20 mm, 2 layers | both | [Gerbers](CAD/pcb/PP-Stack-PCB-v2-gerbers.zip) for any board house, see [Ordering the PCB](#ordering-the-pcb) |
| 1 | Rotary encoder, Alps EC12E2420801 | both | [LCSC](https://www.lcsc.com/product-detail/C351236.html) · [AliExpress](https://www.aliexpress.com/item/1005006583646763.html) · [Mouser](https://www.mouser.com/ProductDetail/688-EC12E2420801) |
| 2 | Push button, SAMZO 2010751102 | Through-hole buttons | [LCSC](https://www.lcsc.com/product-detail/C41416693.html) · [AliExpress](https://www.aliexpress.com/item/1005005854541077.html) (pick the 5.8 × 5.8 mm, flat head, no lock version) |
| 2 | Push button, Panasonic EVQ9P105M | SMD buttons | [LCSC](https://www.lcsc.com/product-detail/C79157.html) · [Mouser](https://www.mouser.com/ProductDetail/667-EVQ-9P105M) |
| 1 | Female header, 1×4, 2.54 mm | both | [LCSC](https://www.lcsc.com/product-detail/C2897367.html) · [AliExpress](https://www.aliexpress.com/item/4001198421663.html) |
| 1 | Long pin header, 1×4, 21 mm | Through-hole buttons | [LCSC](https://www.lcsc.com/product-detail/C51353.html) · [AliExpress](https://www.aliexpress.com/item/1005001514058091.html) ("21mm") |
| 1 | Long pin header, 1×4, 17 mm | SMD buttons | [LCSC](https://www.lcsc.com/product-detail/C5156622.html) · [AliExpress](https://www.aliexpress.com/item/1005001514058091.html) ("17mm") |
| 1 | ZH1.5 connector, 5 pin, right angle | both | [LCSC](https://www.lcsc.com/product-detail/C2845568.html) · [AliExpress](https://www.aliexpress.com/item/1005012352793560.html) |
| 8 | M2 × 8 self-tapping screw, pan head | both | [AliExpress](https://www.aliexpress.com/item/4000982209705.html) ("8mm") · [LCSC](https://www.lcsc.com/product-detail/C357361.html) (often out of stock) |
| 1 | Inner frame + housing | each its own | Print from [`CAD/printed/`](CAD/printed/), see below |
| | ZH1.5 cable, 5 pin (optional) | both | [LCSC](https://www.lcsc.com/product-detail/C53155206.html) · [AliExpress](https://www.aliexpress.com/item/1005001649158434.html) |

The pin headers come as 1×40 strips: snap off four pins. The ZH connector is the right-angle kind; a straight one can work too, depending on the rest of the geometry.

> [!IMPORTANT]
> The frame slides up and down inside the housing, so print both accurately. Each build has one STEP file in [`CAD/printed/`](CAD/printed/) with both parts in it. They need only a minimal gap: enough for smooth push and pull, not so much that the knob wobbles. Test-fit the frame in the housing before you assemble anything.

You'll also need a soldering iron, flush cutters and a small screwdriver. For the SMD buttons, use a fine tip or a soldering hot plate.

### Ordering the PCB

Upload [`PP-Stack-PCB-v2-gerbers.zip`](CAD/pcb/PP-Stack-PCB-v2-gerbers.zip) as it is to JLCPCB, PCBWay or any other board house. Both builds use the same board.

| Setting | Value |
|:--|:--|
| Layers | 2 |
| Size | 20 × 20 mm |
| Thickness | 1.6 mm (the stack heights assume it) |
| Quantity | 2 per build, so the usual minimum of 5 covers two builds |
| Stencil | Not needed. Only the SMD buttons use paste, 4 pads per board |

The [schematic](CAD/pcb/PP-Stack-PCB-v2-schematic.pdf) and the [EasyEDA Pro project](CAD/pcb/PP-Stack-PCB-v2.epro2) are in the same folder if you want to change the board.

## One PCB, two jobs

<picture><source media="(prefers-color-scheme: dark)" srcset="docs/img/flip-dark.gif"><img align="right" width="50%" vspace="12" src="docs/img/flip.gif" alt="Top board flips onto the bottom board, dot over ring"></picture>

The headers decide which board is which. The bottom board gets the long pin header in **U5**, next to the ring. The top board gets the female header in **U4**, next to the dot.

U4 and U5 are mirror images, so when the top board flips onto the bottom one the headers line up, dot over ring. Each board leaves the other slot empty (hatched in the pictures).

<br clear="right"><br>

## How it works

<picture><source media="(prefers-color-scheme: dark)" srcset="docs/img/through-hole/how-it-works-dark.png"><img align="right" width="50%" vspace="12" src="docs/img/through-hole/how-it-works.png" alt="Cutaway showing the bar between the two buttons"></picture>

The two boards, the inner frame and the encoder move together as one stack inside the housing. A bar fixed across the housing sits between the two push buttons.

Push the knob and the top board's button hits the bar. Pull it and the bottom board's button does. The buttons' own springs bring the knob back to centre.

| CN2 pin | Signal |
|:---:|:---|
| 1 | GND |
| 2 | PULL |
| 3 | PUSH |
| 4 | CCW (A) |
| 5 | CW (B) |

<br clear="right"><br>

## Files

| Folder | What's in it |
|:--|:--|
| [`CAD/pcb/`](CAD/pcb/) | Gerbers to order the board, schematic, EasyEDA Pro project |
| [`CAD/printed/`](CAD/printed/) | Inner frame + housing for each build (STEP, one file per build), knob |
| [`CAD/assembly-example/`](CAD/assembly-example/) | Example assembly of each build (STEP) |
| [`docs/`](docs/) | Assembly instructions for each build, images |
