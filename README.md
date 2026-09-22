# Quitting Time

A browser stealth game: it's 18:00 on floor 12 and you have to get out of the
sales bullpen without a single manager making eye contact with you.

**Play:** open `index.html` in any modern browser. No build step, no dependencies
beyond a single CDN script tag (three.js r128).

## Controls

| Key | Action |
| --- | --- |
| `W` `A` `S` `D` / arrows | walk |
| `Shift` | crouch — slower, quieter, low enough to hide behind cubicle partitions |
| `Q` `E` (or drag) | swing the camera |
| `R` | restart · `Esc` pause |

## Rules

1. Collect your bag at desk 12-C.
2. Reach the east stairwell.
3. Five people can spot you: the regional manager laps the north corridor, a
   supervisor and HR walk the vertical aisles, the floor manager watches from
   the glass office (glass does not block his line of sight), and a colleague
   lurks by the copier. Fill any one person's exposure meter and you are in a
   "quick chat" until seven.

Line of sight is a real raycast — partitions, pillars, cabinets and plants block
it, desks and glass do not. Crouching drops your head below partition height.

## Structure

Single file. `index.html` holds the markup, the HUD styles and the whole game:
procedural canvas textures, the office geometry, the vision/detection model, the
minimap and a small WebAudio synth. There are no image or model assets.
