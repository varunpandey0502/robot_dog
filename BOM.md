# Robot dog: components and shopping list

Everything needed to build the robot in `solidcraft/robot_dog_assembly_v8.solidcraft`. Leg names are `FL`, `FR`, `RL` and `RR` (front or rear, left or right).

## What to buy

### Servos

| Item | Spec | Needed | Buy |
|---|---|---:|---:|
| MG996R servo | Standard position-control version, **not** continuous rotation. Must include a double-arm horn, centre screw and horn screws. | 12 | 13 |

The datasheet gives about 120° of travel (±60°), while many sellers list 180°. The legs are designed for up to ±80°, so a 180° servo gets the full range. A 120° servo still works with slightly less reach, as the [README limits](README.md#kinematics) show.

Each servo kit supplies the parts below, so these are not bought separately:

| From the kit | Needed | Used for |
|---|---:|---|
| Double-arm horn, 39 mm tip to tip | 12 | Fits the recess in each coxa and upper link |
| Horn centre screw | 12 | Holds the horn on the servo spline |
| M2 self-tapping horn screws, 8 mm long at most | 24 | 2 per horn, into Ø1.6 × 6 mm pilots |

Horn shapes vary between sellers. Check yours against the sizes in [the README](README.md#check-these-before-printing-everything).

### Fasteners

Stainless or zinc-plated steel. "Buy" includes a few spares.

| Item | Standard | Needed | Buy | Used for |
|---|---|---:|---:|---|
| M3 × 16 pan or socket head | ISO 7045 or ISO 4762 | 48 | 50 | Servo ears |
| M3 × 16 countersunk, hex socket, 90° | ISO 10642 | 20 | 25 | Top plate |
| M3 × 25 socket head | ISO 4762 | 12 | 15 | Static bars (8), handle (4) |
| M3 × 35 socket head, partial thread preferred | ISO 4762 | 4 | 6 | Foot cross pins |
| M4 × 25 button head | ISO 7380 | 8 | 10 | Knees |
| M4 × 35 button or socket head | ISO 7380 or ISO 4762 | 4 | 6 | Foot pins |
| M3 nyloc nut | ISO 10511 or DIN 985 | 4 | 6 | Cross pins |
| M4 nyloc nut | ISO 10511 or DIN 985 | 12 | 15 | Knees (8), foot pins (4) |
| M3 flat washer, 7 mm OD | ISO 7089 | 56 | 60 | Servo screws (48), cross pins (8) |
| M4 flat washer, 9 mm OD | ISO 7089 | 16 | 20 | Knee nuts (8), foot pins (8) |

### Filament

| Material | For | Solid volume | Buy |
|---|---|---:|---|
| PLA or PETG | 29 rigid parts | 2.60 L (3.2 kg of PLA if printed 100% solid) | 3 kg |
| TPU, shore 85A–95A | 4 foot boots | 66 cm³ (about 80 g) | One 250 g spool or larger |

At typical wall and infill settings, expect the rigid parts to use about 1.3–2.3 kg.

### Electronics

**These are not part of the CAD model and have no mounting points yet.** Choose them to suit your control setup. The body interior is open and reachable from the top.

| Item | Requirement |
|---|---|
| Servo driver | At least 12 PWM channels, such as a 16-channel PCA9685 board |
| Controller | Any board that can drive it, such as an ESP32 or Raspberry Pi |
| Servo power | Within the servo's 4.8–7.2 V range, on a separate supply from the logic. Each servo draws 0.5–0.9 A running and 2.5 A at stall at 6 V, so 12 can reach 30 A in the worst case. Size the supply, wiring and fuse for that. |
| Battery or bench supply | To match the servo power rail |
| Servo extension leads | Only if the stock 30 cm leads don't reach your driver |
| Cable ties or sleeving | For the leg cable loops |

### Tools

| Tool | For |
|---|---|
| 2.5 mm hex key | M3 socket heads, M4 button heads |
| 2 mm hex key | M3 countersunk screws |
| 3 mm hex key | M4 socket heads, if used for the foot pins |
| 5.5 mm and 7 mm spanners or nut drivers | M3 and M4 nyloc nuts |
| Phillips driver, **at least 125 mm long and under 6 mm in shaft diameter** | Servo centre screws, including the hip servos through the coxa access bore |

## Every component

### Printed (33 parts)

Print each file once. The `{FL,FR,RL,RR}` names stand for four separate files, one per leg, each available as `.stl` in `stl/` and `.step` in `step/`. Print each leg's own file rather than repeating one.

| Part | Files (`.stl` and `.step`) | Qty | Material | Size, mm | Solid volume each, cm³ |
|---|---|---:|---|---|---:|
| Body | `Chassis` | 1 | PLA or PETG | 360 × 230 × 60 | 1004.5 |
| Top plate | `TopPlate` | 1 | PLA or PETG | 359 × 230 × 5 | 218.3 |
| Handle | `Handle` | 1 | PLA or PETG | 180 × 55 × 20 | 103.2 |
| Front static bar | `BarFront` | 1 | PLA or PETG | 230 × 65 × 36.5 | 257.6 |
| Rear static bar | `BarRear` | 1 | PLA or PETG | 230 × 65 × 36.5 | 257.6 |
| Coxa (hip carrier, holds 2 leg servos) | `Coxa_{FL,FR,RL,RR}` | 4 | PLA or PETG | 123 × 64 × 27 | 89.4 |
| Inner upper link | `UpperIn_{FL,FR,RL,RR}` | 4 | PLA or PETG | 96 × 20 × 10 | 15.9 |
| Outer upper link | `UpperOut_{FL,FR,RL,RR}` | 4 | PLA or PETG | 96 × 20 × 10 | 15.9 |
| Inner lower link | `LowerIn_{FL,FR,RL,RR}` | 4 | PLA or PETG | 140 × 22 × 7.5 | 17.7 |
| Outer lower link | `LowerOut_{FL,FR,RL,RR}` | 4 | PLA or PETG | 140 × 22 × 7.5 | 17.8 |
| Foot core | `Foot_{FL,FR,RL,RR}` | 4 | PLA or PETG | 71.5 × 44.8 × 44.8 | 32.9 |
| Foot boot | `FootBoot_{FL,FR,RL,RR}_TPU` | 4 | TPU 85A–95A | 48 × 48 × 29.8 | 16.5 |

### Bought parts shown in the CAD assembly (40 bodies)

| CAD bodies | Count | Real part |
|---|---:|---|
| `HipServo_XX` | 4 | MG996R, hip roll |
| `ServoIn_XX`, `ServoOut_XX` | 8 | MG996R, leg drive |
| `HornHip_XX`, `HornIn_XX`, `HornOut_XX` | 12 | Double-arm horn from the servo kit |
| `KneePinIn_XX`, `KneePinOut_XX` | 8 | M4 × 25 button head |
| `FootPin_XX` | 4 | M4 × 35 |
| `CrossPin_XX` | 4 | M3 × 35 |

Screws other than the pins, plus all nuts and washers, are not modelled. The static-bar pivot pins are printed as part of `BarFront` and `BarRear`, and the design uses no bearings.

## Where each fastener goes

The servo, top plate, bar and handle screws thread directly into Ø2.8 mm pilot holes in the plastic. No inserts are needed.

| Joint | Qty | Fastener | Depth or stack | Notes |
|---|---:|---|---|---|
| Servo ear to body or coxa | 48 | M3 × 16, washer | 2.5 ear + 0.5 washer, 13 mm into a 14 mm pilot | Leave out the rubber grommets |
| Top plate to body | 20 | M3 × 16 countersunk | 5 plate, 11 mm into a 12 mm pilot | Ø6.6 × 90° countersink |
| Static bar to body | 8 | M3 × 25 socket | 17 through the bar, 8 mm into a 9 mm pilot | Head sits in a Ø6.2 × 3 counterbore |
| Handle to top plate | 4 | M3 × 25 socket | 5 plate, 20 mm into a 21 mm pilot | Fitted from under the plate, before the plate goes on |
| Inner knee | 4 | M4 × 25 button, 1 washer, nyloc | 15.5 clamped | Head in the Ø8.5 × 2.5 recess on the inner face of `LowerIn`, **no washer under the head**. Washer and nut on the outer face of `UpperIn`. |
| Outer knee | 4 | M4 × 25 button, 1 washer, nyloc | 18 clamped | Head on the inner face of `UpperOut`, no washer. Washer and nut on the outer face of `LowerOut`. |
| Foot pin | 4 | M4 × 35, 2 washers, nyloc | 26 clamped | Through `LowerIn`, foot and `LowerOut` |
| Cross pin | 4 | M3 × 35, 2 washers, nyloc | 26 between outer faces | Must slide in its 3.2 mm slots, so keep it loose |
| Horn to coxa or upper link | 24 | M2 self-tapping, from kit | Ø1.6 × 6 mm pilot | 2 per horn |
| Horn to servo spline | 12 | Centre screw, from kit | n/a | Reached through the access hole in each part |

Tighten knee and foot nuts only until the play is gone and the joint still turns freely. The links have 0.5 mm running gaps, and overtightening clamps them together.
