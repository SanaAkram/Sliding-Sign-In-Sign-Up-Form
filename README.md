# Sliding Sign-In / Sign-Up Form

A **pure HTML, CSS and JavaScript** login and registration screen where the two forms live on one page and a coloured panel **slides across** to switch between *Sign in* and *Sign up*. It is a UI component only — the forms have no backend and submit to `#` — meant as a starting point or reference for an authentication page. (This is a fork of a public tutorial project, kept for study and reuse.)

## How it works

```
index.html   two <form>s (sign-in, sign-up) stacked in .signin-signup, plus two .panel blocks (left "New here ?", right "One of us ?") with the toggle buttons
style.css    positions the forms and panels absolutely; a huge blue-gradient circle (.container:before) sweeps across the screen as the "sliding" background
app.js       adds / removes the class  sign-up-mode  on .container when a toggle button is clicked
```

- Clicking **Sign up** (`#sign-up-btn`) adds `sign-up-mode` to `.container`; the CSS selectors `.container.sign-up-mode …` then move the gradient circle, the form container (a `1s` transition with a `0.7s` delay) and the panel content, and cross-fade the two forms.
- Clicking **Sign in** (`#sign-in-btn`) removes the class and everything slides back.
- The layout collapses to a stacked version on narrow screens through media queries in `style.css`.

```
.
├─ index.html
├─ style.css
├─ app.js
└─ img/
   ├─ log.svg          illustration on the "New here?" panel
   └─ register.svg     illustration on the "One of us?" panel
```

## Run it

No build step and no dependencies.

```bash
git clone https://github.com/SanaAkram/Sliding-Sign-In-Sign-Up-Form.git
cd Sliding-Sign-In-Sign-Up-Form
```

Open `index.html` in a browser, or serve the folder:

```bash
python -m http.server 8000      # http://localhost:8000
```

Font Awesome icons are loaded from the Font Awesome CDN kit and the Poppins font from Google Fonts, so an internet connection is needed for the icons and typography.

## Using it in your own project

1. Copy the two `<form>` blocks and the panels from `index.html`, `style.css` and `app.js`.
2. Give the `<input>`s `name` attributes and replace `action="#"` with your endpoint, or intercept the `submit` event and call your API with `fetch`.
3. Replace the placeholder panel text and the SVGs in `img/`.

## Customising

- Colours — buttons use `#5995fd` (hover `#4d84e2`) and the sweeping background is the gradient `#4481eb → #04befe`; search for those hex values in `style.css`.
- Fonts — change the `@import` at the top of `style.css`.
- Social buttons — Facebook / Twitter / Google / LinkedIn icons are placeholders (links point to `#`).
- The panel text is Lorem ipsum placeholder copy.
