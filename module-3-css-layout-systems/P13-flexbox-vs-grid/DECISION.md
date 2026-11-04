# P13 – Choosing Between Flexbox and Grid

## The one-line rule

- **Flexbox** lays items out along **one axis** (a row *or* a column). The **content** decides the sizes.
- **Grid** lays items out in **two axes** (rows *and* columns). The **layout** decides the sizes.

## Comparison

| Question | Flexbox | Grid |
|----------|---------|------|
| Dimensions | 1D | 2D |
| Who controls size? | Content | Container (track definitions) |
| Best for | Components | Page and section layouts |
| Alignment tools | `justify-content`, `align-items`, `gap`, `margin: auto` | `grid-template-areas`, `place-items`, `gap`, spanning |
| Wrapping | `flex-wrap` – each line is independent | Items always snap to shared rows and columns |

## Decisions made in `index.html`

| Part of the page | Choice | Why |
|------------------|--------|-----|
| Overall page frame (header, sidebar, content, footer) | **Grid** | Needs rows **and** columns; `grid-template-areas` describes the layout and restacks easily on mobile. |
| Header (logo left, nav right) | **Flexbox** | A single row; `justify-content: space-between` is exactly what is needed. |
| Navigation links | **Flexbox** | One row of items with a `gap`. |
| Tag list in the sidebar | **Flexbox** | Items have different widths and should wrap naturally. |
| Card gallery | **Grid** | `repeat(auto-fit, minmax(220px, 1fr))` gives equal, aligned columns. |
| Inside each card (title, text, button) | **Flexbox** | A vertical stack where the text grows (`flex-grow: 1`) so buttons line up at the bottom. |
| Footer (two items, space between) | **Flexbox** | One row, simple distribution. |

## How to decide quickly

1. Am I arranging things in a **single line**? → Flexbox.
2. Do I need items to line up in **both** directions? → Grid.
3. Do I want the **content** to shape the layout? → Flexbox.
4. Do I want to **define the layout first** and place content into it? → Grid.
5. Still unsure? Grid for the outer structure, Flexbox for the pieces inside it.

## They work together

Grid and Flexbox are not competitors. Here, Grid builds the page frame and card gallery, while Flexbox arranges the content inside each grid area. A grid item can itself be a flex container, and a flex item can contain a grid.
