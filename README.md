# JND Test – Find Your Just Noticeable Difference

An interactive experiment to measure the **smallest difference in grey that your eye can detect** on your own screen, and to test **Weber's law**.

**Live demo:** https://hanaamaswada.github.io/jnd-test/

## The idea

Weber's law says that the smallest change we can notice (the *just noticeable difference*, ΔI) is a **constant fraction** of the starting intensity I:

```
ΔI / I ≈ k   (constant)
```

So a bright grey needs a bigger step than a dark grey before we see a difference. This tool lets you check whether that holds on your screen.

## The experiment

1. Two grey fields touch in the middle. Both start at the same value **RGB (I, I, I)**.
2. Raise the right field one step at a time (I + 1, I + 2, …) until you can **only just** see the edge between them.
3. Press **"I can see the edge"** to record ΔI. Repeat 2–3 times for the same I.
4. Do this for **I = 20, 100 and 200**.
5. The table computes the mean ΔI and **ΔI / I** for each level.

Tip: use **"Hide numbers"** so the value on screen does not bias you.

## Why the ratio is often not constant

Screens do not turn RGB numbers into light linearly. The **sRGB gamma curve** makes the light output grow much faster than the RGB value. A step of +1 at RGB 20 changes the light by a much larger fraction than +1 at RGB 200.

That is why the table has two ratio columns:

| Column | Meaning |
|---|---|
| **ΔI / I** | the ratio in RGB numbers |
| **Δ luminance / luminance** | the same step converted to actual light output with the standard sRGB curve |

Comparing the two shows how much of the "failure" of Weber's law comes from the screen itself. At very dark levels, viewing conditions also matter: reflections and room light raise the effective background, so dark greys are harder to separate.

## What it means for data visualization

- Equal steps in RGB do **not** look like equal steps. A color scale should be built so that **perceived** lightness changes evenly, not the raw numbers.
- Neighbouring classes of a scale must differ by more than one JND, or readers will not see the difference, especially in the **dark** part of the scale.
- Small differences that are clear on one screen may vanish on another screen, a projector or in a bright room.

## How to use

Open the [live demo](https://hanaamaswada.github.io/jnd-test/) or download `index.html` and open it in any browser.

- Keep the zoom at 100 %, normal screen brightness, and avoid glare.
- Keyboard: **↑ / +** raises the right field, **↓ / −** lowers it.
- **Copy table** copies your results to share or compare.

Results are personal: they depend on your eyes, your screen and your room. Try it and compare with others!

## Built with

Plain HTML, CSS and JavaScript in a single file, with no libraries and no build step.

## Background

Built as part of the *Data Visualization* course in the Master's program in Intelligent Systems Engineering (Data Science) at Palestine Polytechnic University.

**Related experiment:** [Same Color Test](https://hanaamaswada.github.io/same-color-test/), where the same color looks different on different backgrounds.

**Author:** Hanaa Maswada · [LinkedIn](https://www.linkedin.com/in/hana-maswada-961b2337b) · [GitHub](https://github.com/HanaaMaswada)
