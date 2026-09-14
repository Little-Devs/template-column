# MOTION.md, Column sketch

MOTION_INTENSITY: 5 (calm editorial, per TOKEN-PLAN). All motion is transform and opacity only.
Implementation: static CSS transitions + one IntersectionObserver in `js/motion.js` (booted by
`js/boot.js`, which sets `<html class="js">`). No scroll listeners, no animation libraries.
Motion is gated behind `prefers-reduced-motion: no-preference`, and a global `reduce` block in
site.css collapses anything left over. Reveals only hide elements when `<html class="js">` is
set, so a no-JS load never shows a blank page.

## Effects

### 1. Column fade-in (reveal on entry)
- What: sections, rows, and hero elements start at `opacity: 0`, `translateY(14px)` and rise to
  rest. Stagger of 80ms per item via `--reveal-i`.
- Trigger: element enters the viewport. `js/motion.js` IntersectionObserver (`threshold: 0.15`,
  `rootMargin: 0 0 -8%`), fires once, then unobserves.
- Reduced motion: observer skipped entirely, `.is-visible` applied immediately on load; CSS hides
  the initial state behind `no-preference`. Elements are never hidden under reduced motion.

### 2. Ledger row hover tint
- What: service journal rows tint to a 5% green wash.
- Trigger: pointer hover on `.ledger-row`.
- Reduced motion: transition duration collapses to 0.01ms via the global reduce block; the tint
  still appears (state feedback, not motion).

### 3. Button lift and press
- What: primary and ghost buttons rise 1px on hover, press down with `scale(0.99)` on
  `:active`, and shift background color.
- Trigger: hover / active on `.btn`.
- Reduced motion: movement removed by the reduce block; color feedback remains.

### 4. Link feedback
- What: text and nav links shift color and underline offset on hover.
- Trigger: hover.
- Reduced motion: color change is instant, no transition.

### 5. FAQ plus rotation
- What: the `+` marker on FAQ summaries rotates 45 degrees to an `x` when a question opens.
- Trigger: native `details` toggle.
- Reduced motion: rotation snaps without transition.

## Non-goals for this sketch
No marquees, parallax, scroll-hijack, infinite loops, or entrance choreography beyond the
staggered fade-in. The thesis "Books that stay balanced" reads as stillness; motion only marks
hierarchy and feedback.
