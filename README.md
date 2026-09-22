# Quitting Time

A browser stealth game: it's 18:00 on level 12 of a Raffles Place tower, the sun
is going down over Marina Bay, and you have to get out of the sales bullpen
without a single manager making eye contact with you.

**Play:** https://mata4pemp.github.io/escape-office-early-game/

**Play:** open `index.html` in any modern browser. No build step, no dependencies
beyond a single CDN script tag (three.js r128).

## Controls

Third-person shooter layout: the mouse aims the camera, `WASD` walks relative to it.

| Input | Action |
| --- | --- |
| Mouse | look around (the page takes pointer lock when you click or start a run) |
| `W` `A` `S` `D` / arrows | walk, relative to where the camera is pointing |
| `Shift` | crouch — slower, quieter, low enough to hide behind cubicle partitions |
| `Q` `E`, or drag | swing the camera without a locked pointer |
| `R` | restart · `Esc` pause and release the mouse |

Releasing the pointer pauses the game; click to resume.

## Rules

1. Collect your bag at desk 12-C.
2. Reach the east stairwell before the last lift goes at 18:36 — a three-minute
   countdown runs down the right-hand side of the screen.
3. Five people can spot you: the regional manager laps the north corridor, a
   supervisor and HR walk the vertical aisles, the floor manager watches from
   the glass office (glass does not block his line of sight), and a colleague
   lurks by the copier.

Being clocked from across the floor does not end the run. It raises that
person's alert, they break off what they were doing and walk towards where they
last saw you — the seated floor manager gets out of his chair to do it. Only
someone within `CATCH_DIST` (3.4 m) of you actually fills the red meter, and you
walk faster than they do, so breaking line of sight and moving is a real escape.

Line of sight is a real raycast — partitions, pillars, cabinets and plants block
it, desks and glass do not. Crouching drops your head below partition height.

Two ways to lose, both with a slow-motion desaturated death shot: **INTERCEPTED**
if someone corners you, **OVERTIME** if the countdown runs out.

## The view

Everything outside the glass is real geometry, not a backdrop, so it parallaxes
as you move: Marina Bay Sands with the SkyPark across its three towers, the
ArtScience Museum, the Singapore Flyer, the Gardens by the Bay supertrees, the
Esplanade domes, Raffles Place towers with lit window grids, and the bay itself
under a sunset gradient. The office sits 45 m up, so you look down on the
neighbouring rooftops — walk to the glass to see the full skyline.

## Structure

Single file. `index.html` holds the markup, the HUD styles and the whole game:
procedural canvas textures, the office geometry, the city, the vision/detection
model, the minimap and a small WebAudio synth. There are no image or model
assets — every texture is drawn to a canvas at load time and every character is
composed from spheres and tapered cylinders.
