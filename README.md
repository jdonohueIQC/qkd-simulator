# Build Your Own QKD — Digital Simulator

A single-page, dependency-free HTML/JS simulator of the IQC "Build Your Own Quantum Key
Distribution" outreach kit. It mirrors the physical apparatus: Alice's half-wave plate
(4 states), an optional Eve with a quarter-wave plate, Bob's half-wave plate + detector
LEDs, a manual pulse button, and an automated key-exchange console.

## Run it

Just open `index.html` in a browser — no build step, no dependencies besides two Google
Fonts loaded over the network.

## Host it on GitHub Pages

1. Create a new repo (or use an existing one) and add these files at the root:
   - `index.html`
   - `assets/logo.png`
2. Push to GitHub.
3. In the repo, go to **Settings → Pages**, set **Source** to the `main` branch (root),
   and save.
4. Your simulator will be live at `https://<your-username>.github.io/<repo-name>/`.

## What it simulates

- **Alice** prepares one of four polarization states (H, +45°, V, −45°), matching the
  four labelled angles on the kit's half-wave plate mount (0°, 22.5°, 45°, 67.5°).
- **Bob** measures in one of two bases (H/V or ±45°), matching the two settings on his
  half-wave plate.
- **Eve**, if switched on, "measures" in H/V or ±45° via a simulated quarter-wave plate.
  If her basis matches Alice's, the state passes through undisturbed; if not, the state
  is randomized before reaching Bob — the same behaviour described in the kit's manual.
- The **automated console** runs a batch of qubits with configurable settings (including
  "random each qubit" for Alice, Bob, and Eve) and an adjustable interception probability
  for Eve, then reports the sifted key and the error rate (QBER) — a quick way to see how
  an eavesdropper introduces detectable errors.
- **CSV export** produces `alice_log.csv` and `bob_log.csv`, each with `n, basis, bit`
  columns, matching the notebooks students keep with the physical kit.

## Credits

Modelled on *Build Your Own Quantum Key Distribution*, IQC Scientific Outreach Team,
University of Waterloo, and the accompanying paper "Interactive and accessible quantum
key distribution modules for introducing students to quantum science and engineering"
(Donohue et al.).
