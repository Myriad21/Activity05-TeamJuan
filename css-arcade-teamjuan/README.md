# Activity 05 — CSS Arcade

## Team Information

**Team Name:** TeamJuan  
**Members:** Trajuan Smith  
**Driver:** Trajuan Smith  
**Navigator:** Trajuan Smith  

---

# Round 1 — Layout Prediction Blitz

## Scenario 1 — Cookie Menu Row

**Prediction:** No response (time expired)  
**Result:** Incorrect  
**Actual:** One row; outer cards touch the edges, with equal space between them.

## Scenario 2 — Tic-Tac-Toe Board

**Prediction:** A 3 × 3 board  
**Result:** Correct  
**Actual:** A 3 × 3 board.

## Scenario 3 — Axis Flip

**Prediction:** Vertically (top-to-bottom)  
**Result:** Incorrect  
**Actual:** Horizontally (left-to-right).

## Scenario 4 — Fraction Launch

**Prediction:** Time between repeats  
**Result:** Incorrect  
**Actual:** Delay before the animation starts.

## Scenario 5 — The Snap-Back

**Prediction:** It snaps back to its starting position.  
**Result:** Correct  
**Actual:** It snaps back to its starting position.

## Scenario 6 — The Missing Heart

**Prediction:** On top of the shirt at 140px / 110px  
**Result:** Incorrect  
**Actual:** In normal flow, with `top`, `left`, and `z-index` ignored.

**Final Score:** 2 / 6

---

# Round 2 — Bug Hunt

## Bug 1 — Flexbox Axis

### Team Diagnosis

The `flex-direction` property sets the direction of the main axis. Since it is set to `column`, the main axis runs vertically, causing the three recipe cards to stack on top of each other instead of appearing in a horizontal row.

### CSS Correction

```css
flex-direction: row;
```

This changes the main axis back to horizontal so the three recipe cards appear in a row.

---

## Bug 2 — Grid Tracks

### Team Diagnosis

There are only two column tracks defined, so the browser places two cells in each row. The remaining cells automatically flow into new rows, creating five rows with the ninth cell alone in the last row.

### CSS Correction

```css
grid-template-columns: repeat(3, 1fr);
```

This defines three equal-width column tracks, allowing the nine cells to form a 3 × 3 board.

---

## Bug 3 — Animation Fill Mode

### Team Diagnosis

The answer should use the first keyframe styles during the delay, then keep the final keyframe styles after the animation ends. The `animation-fill-mode` property controls this, and `both` applies the keyframe styles both before and after the animation.

### CSS Correction

```css
animation-fill-mode: both;
```

This applies the first keyframe styles during the animation delay and preserves the final keyframe styles after the animation finishes.

---

## Bug 4 — Positioning and Z-Index

### Team Diagnosis

The heart is using `position: static`, so `top` and `left` do not position it, and `z-index` does not affect its stacking as intended. Changing the heart to `position: absolute` allows those properties to work and positions it relative to its positioned parent.

### CSS Correction

```css
position: absolute;
```

This allows the heart's `top`, `left`, and `z-index` properties to work as intended.

---

# Round 3 — Build Challenge

## Retro Tic-Tac-Toe Cabinet

The final build is a retro arcade-themed Tic-Tac-Toe page demonstrating Flexbox, CSS Grid, keyframe animation, positioning and layering, micro-interactions, and responsive design.

---

## Checkpoint 1 — Flexbox Layout

**Selector:** `.cabinet-header`

The header uses `display: flex` with `justify-content: space-between`, `align-items: center`, and `gap` to position the title and navigation.

![Checkpoint 1 — Flexbox Layout](images/checkpoint1.png)

---

## Checkpoint 2 — CSS Grid Board

**Selector:** `.game-grid`

The game board uses `display: grid` with `grid-template-columns: repeat(3, 1fr)` to create three equal-width columns for the 3 × 3 Tic-Tac-Toe board.

![Checkpoint 2 — CSS Grid Board](images/checkpoint2.png)

---

## Checkpoint 3 — Keyframe Animation

**Selectors:** `.marquee-text` and `@keyframes press-start`

The `Press Start` text uses an animation with `0%`, `50%`, and `100%` keyframes that changes its position with `transform` and changes its color. The animation also uses a delay and the `both` fill mode.

![Checkpoint 3 — Keyframe Animation](images/checkpoint3.png)

---

## Checkpoint 4 — Layered Composition

**Selectors:** `.layer-stack` and `.layer`

`.layer-stack` uses `position: relative` as the positioning parent. The child layers use `position: absolute` with different `z-index` values to stack the background X, `PLAYER 1` text, and `WINS!` text.

![Checkpoint 4 — Layered Composition](images/checkpoint4.png)

---

## Checkpoint 5 — Micro-Interaction

**Selectors:** `.tile:hover` and `.tile:focus-visible`

The Tic-Tac-Toe tiles use transitions on `transform` and `box-shadow`. Hovering or keyboard-focusing a tile enlarges it and adds a neon glow.

![Checkpoint 5 — Micro-Interaction](images/checkpoint5.png)

---

## Checkpoint 6 — Professional & Responsive

**Selector:** `@media (max-width: 768px)`

At screen widths of 768px or less, `.cabinet-header` changes to `flex-direction: column`, stacking the title and navigation for smaller screens. The Tic-Tac-Toe tiles also become smaller to better fit the viewport.

![Checkpoint 6 — Responsive Design](images/checkpoint6.png)