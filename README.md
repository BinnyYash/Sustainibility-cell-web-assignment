# Sustainability Cell, IIT Bombay — Web Convener Assignment

Hero section redesign for the Sustainability Cell website (Q1) and a written proposal for a campus sustainability map (Q2).

Reference site: https://gymkhana.iitb.ac.in/~sustainabilitycell/

## Q1. Hero Section Redesign

A redesigned hero that keeps the existing theme of the current website but replaces the static globe with a live, interactive dotted Earth. You can drag the globe to rotate it, and tap or click it to make it spin faster. Small satellites orbit around it, and the Sustainability Cell logo in the nav has a soft pulsing green glow. The whole hero is one self-contained `index.html` file plus the `land.js` coordinate dataset and the `logo.png` image. No build step.

## Q2. Campus Sustainability Map

See [`Q2_Sustainability_Map_Proposal.md`](./Q2_Sustainability_Map_Proposal.md) for Question 2

## Files

```
.
├── index.html                          # Q1 hero section
├── land.js                             # Land coordinate dataset used by the globe
├── logo.png                            # Sustainability Cell logo
├── Q2_Sustainability_Map_Proposal.md   # Q2 written proposal
└── README.md
```
## Live URL

https://binnyyash.github.io/Sustainibility-cell-web-assignment/

## Additional notes about my implementation

I built this myself, with some help from an AI as a teacher and code helper, which the brief permits. Here are the choices I made and how each piece was put together:

**Background colour.** I matched the dark navy-to-teal gradient and the lime-green accent to the current Sustainability Cell website by picking the colours off a screenshot of the live site, so the redesigned hero sits naturally next to the existing identity instead of looking like a different brand.

**Earth globe.** Instead of using a 3D library, I built the globe out of dots on an HTML canvas. Each dot is a coordinate on a sphere, rotated every frame and projected to 2D. Front-facing dots are drawn bigger and brighter, back-facing dots fade. That depth shading is what makes a flat circle of dots actually read as a 3D ball.

**Land vs ocean.** The ocean is drawn as a shaded blue circle, and the green dots are placed only where there is actual land. The land coordinates come from `land.js`, which I got from Claude. The rendering code that uses the dataset (the rotation math, the projection, the front/back check, the colours) is in `index.html`.

**Earth's orientation (intentional).** I placed the globe upside down on purpose, with the North Pole pointing down and the South Pole pointing up, instead of the textbook orientation everyone sees from school onwards. Earth's real 23.5 degree axial tilt is still applied, so the leaning axis itself is accurate, but the whole planet is inverted. The reason is conceptual: sustainability is about seeing the planet differently from how we are used to seeing it, and a flipped Earth is a quiet visual cue that gets people to pause and notice. It also reflects the fact that "north up" is a convention, not a rule, and looking at the world from a fresh angle is exactly what the Sustainability Cell is asking people to do.

**Position.** I placed the Earth on the lower right side of the hero, so the headline has space on the left and the globe feels grounded rather than floating in the middle.

**Spin on tap.** Each tap or click on the globe bumps up its spin speed. Taps stack, so the more you tap the faster it spins, up to a cap. When you stop, the speed eases back down to a gentle idle. I did this with a `speed` variable that gets bumped on click and slowly drifts back to the base value every frame.

**Drag to rotate.** A pointer-drag handler that adjusts the rotation angles directly, so you can manually rotate the globe and look at any part of it.

**Satellites.** I added small dots that revolve around the Earth like satellites in orbit, to give the hero more life and tie into the space theme.

**Logo animation.** I used the official Sustainability Cell logo as a PNG and added a slow pulsing green glow around it using a CSS keyframe animation, so it feels alive in the nav without being distracting.


