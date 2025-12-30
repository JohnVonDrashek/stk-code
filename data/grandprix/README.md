# Grand Prix

Grand Prix series definitions that group multiple tracks into championship races.

## Purpose

Grand Prix files define multi-track racing series where players compete across several tracks with cumulative scoring. The game ships with four main Grand Prix series of increasing difficulty, plus a tutorial definition.

## File Format

### Grand Prix (`.grandprix`)

```xml
<supertuxkart_grand_prix name="Penguin Playground">
    <track id="sandtrack"      laps="3" reverse="false"/>
    <track id="scotland"       laps="3" reverse="false"/>
    <track id="abyss"          laps="3" reverse="false"/>
    <track id="volcano_island" laps="2" reverse="false"/>
    <track id="hacienda"       laps="3" reverse="false"/>
</supertuxkart_grand_prix>
```

### Tutorial (`.tutorial`)

```xml
<tutorial id="basicdriving" name="..." description="..."
    major="single" minor="normal" gp="canyon"
    difficulty="easy" karts="1" position="1"/>
```

## Grand Prix Series

| File | Name | Tracks |
|------|------|--------|
| `1_penguinplayground.grandprix` | Penguin Playground | 5 tracks |
| `2_offthebeatentrack.grandprix` | Off the Beaten Track | 5 tracks |
| `3_tothemoonandback.grandprix` | To the Moon and Back | 5 tracks |
| `4_atworldsend.grandprix` | At World's End | 5 tracks |

## Key Attributes

| Attribute | Description |
|-----------|-------------|
| `name` | Display name shown in menus |
| `id` | Track identifier (must match track folder name) |
| `laps` | Number of laps for this track in the GP |
| `reverse` | Run track in reverse direction |

## How the Game Uses These Files

The Grand Prix manager loads these files to populate the GP selection menu. When a GP starts, tracks are raced in order with points awarded based on finishing position. Total points determine the GP winner. GP challenges in `challenges/` reference these by their filename ID.
