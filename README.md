# Charges in Motion: Electric Circuits Demo

An interactive, browser-based demo of the basic concepts of electric circuits, available as separate English and Korean pages.

Created by **Claude Opus 5.5**, based on the lecture notes by **Sang Hoon Lee (이상훈)**.

> **한국어 요약:** 전류, 저항, 옴의 법칙, 기전력, 키르히호프 법칙 등 전기회로의 기본 개념을 직접 조작해 볼 수 있는 인터랙티브 웹 데모입니다. 이상훈(Sang Hoon Lee)의 강의 노트를 바탕으로 Claude Opus 5.5가 만들었습니다. 한국어 페이지는 `circuits-ko.html`입니다.

## Files

| File | Description |
| --- | --- |
| `circuits-en.html` | American English version |
| `circuits-ko.html` | Korean version (한국어) |
| `README.md` | This file |

Each page is a single self-contained HTML file with inline CSS and JavaScript and no build step or dependencies. The only external request is to Google Fonts for IBM Plex Sans KR; if it can't load, the page falls back to system fonts. Each page links to the other language in its top bar.

## Running it

Open either HTML file directly in a modern browser, or serve the folder locally:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000/circuits-en.html
```

### Publishing on GitHub Pages

1. Push these files to a repository.
2. In **Settings → Pages**, choose **Deploy from a branch** and select your branch and root folder.
3. Visit `https://<user>.github.io/<repo>/circuits-en.html` or `.../circuits-ko.html`.

If you want a landing page at the site root, add an `index.html` that links to both versions, or copy one of them to `index.html`. If you copy one, update the language-switch link in the other page so it points to `index.html`.

## What's inside

The six sections follow the order of the lecture notes. Every value is recomputed live as you move the controls.

1. **Current, current density, and drift speed:** An animated wire shows electrons jittering randomly while drifting slowly against the field. Drift speed is computed from *i* = *nAev*<sub>d</sub> using real carrier densities for copper, aluminum, and silver. An optional narrow section shows that the count of charges crossing a cross-section stays the same while *J* doubles. You can switch the display between electrons and conventional positive charges.
2. **Resistance and resistivity:** A wire resizes as you change its length and cross-section, giving *R* = *ρL*/*A*. It covers eight materials with temperature dependence *ρ* − *ρ*<sub>0</sub> = *ρ*<sub>0</sub>*α*(*T* − *T*<sub>0</sub>) and a *ρ*–*T* graph.
3. **Ohm's law:** An *i*–*V* graph compares a resistor with a pn-junction diode. A chord from the origin shows whether *V*/*i* stays constant, making the point that *V* = *iR* is a definition and not Ohm's law. A side note covers the microscopic model *ρ* = *m*/(*e*²*nτ*).
4. **EMF, internal resistance, and power:** A single-loop circuit with internal resistance *r* shows a potential-around-the-loop graph and a breakdown of power into *P*<sub>emf</sub> = *P*<sub>R</sub> + *P*<sub>r</sub>. A grounding switch (point a or b) shows that changing the ground only shifts potentials.
5. **Series and parallel:** You can toggle between connections and watch the current animate in each branch. A table lists each resistor's current and voltage, along with *R*<sub>eq</sub>.
6. **Multiloop circuits and Kirchhoff's rules:** This is the two-battery, three-resistor circuit from the notes. Assumed and actual current directions are shown together, and negative results are labeled as flowing opposite to the assumed direction. A loop selector shows the left, right, or outer loop equation with numbers substituted, alongside a check of the junction rule.

## Notes on the model

- Material constants are typical room-temperature textbook values: resistivity at 20 °C, temperature coefficient α, and free-electron density *n*.
- The diode uses an idealized Shockley equation, *i* = *I*<sub>s</sub>(e<sup>*V*/*nV*<sub>T</sub></sup> − 1), with parameters chosen so the curve fits the plotted range.
- The drift-speed animation is deliberately exaggerated; the real drift speed is shown in the readout.
- The pages follow the system light or dark setting and respect `prefers-reduced-motion`, which pauses the animations.

## Credits

- Lecture notes: Sang Hoon Lee (이상훈)
- Demo design and code: Claude Opus 5.5

## License

No license has been chosen yet. Add a `LICENSE` file before publishing if you want others to reuse the code, and confirm with the author of the lecture notes how their material may be shared.
