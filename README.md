# Cardiac Electrophysiology Teaching Tool

A single-file, browser-based teaching tool for cardiac electrophysiology. It visualizes the normal cardiac conduction pathway inside an anatomic-style heart framework and animates how depolarization travels from the sinus node through the atria, AV node, His-Purkinje system, and ventricles. It also shows a simplified vector-cardiography-style net electrical vector and rhythm-specific schematic ECG strips.

The project was designed for **Electrophysiology/Cardiology fellows, residents, medical students, and educators** who want a visual way to teach normal conduction, reentry circuits, pre-excitation, and ventricular arrhythmias.

> This is an educational visualization, not a diagnostic ECG interpretation tool.

## Features

- **Standalone HTML/CSS/JS file**  
  No build step, package manager, backend, or external dependencies required.

- **Anatomic-style heart framework**  
  The conduction system is displayed inside a heart-shaped anatomical outline rather than as a purely abstract block diagram.

- **Animated normal conduction**  
  Shows activation from the SA node through atrial myocardium, AV nodal delay, His bundle, bundle branches, Purkinje system, and ventricular activation.

- **Vector cardiography teaching layer**  
  Includes a simplified frontal-plane net-vector arrow and VCG-style loop to show the general direction and organization of depolarization.

- **Selectable arrhythmia mechanisms**  
  Each rhythm updates the animation, vector behavior, schematic ECG strip, and teaching notes.

- **Built-in rhythm strip panel**  
  Provides schematic, rhythm-specific ECG patterns for teaching mechanism rather than exact clinical measurement.

- **Interactive controls**
  - Play / pause animation
  - Reset animation
  - Speed control
  - Rhythm selector buttons

## Included Rhythms and Mechanisms

The tool currently includes:

| Rhythm / Mechanism | Teaching Focus |
|---|---|
| Normal sinus rhythm | SA node activation, AV nodal delay, His-Purkinje conduction, organized QRS vector |
| PAC | Premature ectopic atrial activation and altered P-wave/vector origin |
| Atrial fibrillation | Chaotic atrial activation, irregular AV nodal filtering |
| Atrial flutter | Organized macroreentry, classically right atrial CTI-dependent flutter |
| MFAT / MAT | Multiple atrial foci with shifting P-wave morphology |
| AVNRT — typical slow-fast | Slow antegrade / fast retrograde AV nodal reentry; short-RP SVT |
| AVNRT — atypical fast-slow | Fast antegrade / slow retrograde AV nodal reentry; long-RP SVT |
| Orthodromic AVRT | AV node antegrade conduction with retrograde accessory pathway limb; usually narrow QRS |
| Antidromic AVRT | Accessory pathway antegrade conduction; wide pre-excited tachycardia |
| WPW pattern | Sinus rhythm with pre-excitation, short PR, delta wave concept |
| AF + WPW | Irregular wide-complex pre-excited AF with variable fusion and high-risk rapid conduction |
| Monomorphic VT | Stable ventricular focus/reentry with consistent wide QRS morphology |
| Polymorphic VT | Changing ventricular activation vector and beat-to-beat morphology |
| Coarse VF | High-amplitude chaotic ventricular activation without organized QRS/vector |
| Fine VF | Low-amplitude chaotic ventricular activation; no organized mechanical output |

Note: **Monomorphic** and **polymorphic** are best used for ventricular tachycardia. Ventricular fibrillation is better described as **coarse** or **fine**, because VF does not have a stable organized QRS morphology or reproducible net vector.

## How to Use

### Option 1 — Open directly

Download or clone the project, then open the HTML file in any modern browser:

```text
index.html
```

No installation is required.

### Option 2 — Run with a local static server

This is useful if you want to test browser behavior the same way it would run from GitHub Pages or another static host.

```bash
python3 -m http.server 8000
```

Then open:

```text
http://localhost:8000/heart_ep_teaching_tool.html
```



## Educational Design Philosophy

This project prioritizes **mechanistic clarity** over perfect ECG fidelity. The goal is to help learners understand:

- where activation starts,
- how it propagates anatomically,
- how reentry circuits differ from focal rhythms,
- how accessory pathways alter ventricular activation,
- why ventricular rhythms produce wide and abnormal vectors,
- and why fibrillation abolishes an organized vector loop.

The ECG strips and vector loops are intentionally schematic. They should be used to teach concepts, not to replace real 12-lead ECG review, invasive EP mapping, or clinical decision-making.

## Important Clinical Teaching Notes

- **AF + WPW** is represented as an irregular, variably wide, pre-excited rhythm because AV nodal filtering may be bypassed through the accessory pathway.
- **AVNRT subtypes** are simplified into typical slow-fast and atypical fast-slow circuit directions.
- **AVRT** is shown as a macroreentrant circuit involving the atrium, AV node/His-Purkinje system, ventricle, and accessory pathway.
- **VT** is shown as ventricular activation outside the normal His-Purkinje sequence, producing a wide QRS and abnormal vector.
- **VF** is shown as chaotic activation with no coherent QRS or reproducible vector.

## Browser Compatibility

The tool uses standard browser technologies:

- HTML5
- CSS3
- SVG
- Vanilla JavaScript
- `requestAnimationFrame`

It should work in current versions of Chrome, Firefox, Safari, and Edge.

## Customization

Because the entire app is contained in one HTML file, it is easy to modify:

- Edit rhythm descriptions and teaching bullets in the JavaScript `modes` object.
- Adjust SVG conduction paths to refine anatomy or circuit diagrams.
- Modify animation functions to change activation timing or vector behavior.
- Edit the CSS variables in `:root` to change colors and visual style.
- Add new rhythms by adding a new mode, ECG pattern, VCG pattern, and animation function.

## Limitations

- The heart anatomy is stylized and not intended to be a precise anatomical rendering.
- Vectors are simplified for teaching and mainly represent a frontal-plane conceptual direction.
- ECG strips are schematic and not calibrated clinical ECG signals.
- The tool does not include patient-specific data, measurements, diagnostic algorithms, or clinical risk stratification.
- Treatment notes are intentionally minimal and should not be used as medical management guidance.

## Future Ideas

Possible future improvements:

- Add 12-lead ECG panels for each rhythm.
- Add a ladder diagram view for SVT mechanisms.
- Add EP intracardiac tracings such as HRA, His, CS, and RV channels.
- Add programmed stimulation examples.
- Add concealed vs manifest accessory pathway examples.
- Add torsades de pointes as a dedicated polymorphic VT subtype.
- Add exportable screenshots for lectures.
- Add bilingual teaching labels.

## License

```text
GPL-3.0 license 

Copyright (c) 2026 Yashar Jomebozorgi
```

## Citation / Attribution

If you use this in a lecture, workshop, or teaching session, attribution is appreciated:

```text
Cardiac Electrophysiology Teaching Tool — interactive HTML/SVG/JavaScript visualization for teaching cardiac conduction, arrhythmia mechanisms, and vector behavior.
```

## Disclaimer

This project is provided for educational purposes only. It is not intended for diagnosis, treatment decisions, emergency care, or replacement of clinical ECG interpretation, electrophysiology consultation, or guideline-based medical management.
