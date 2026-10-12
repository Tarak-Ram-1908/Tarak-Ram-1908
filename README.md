# Alahari Tarak Ram
**B.Tech in Computer Science & Engineering | IIITDM Kancheepuram**
*Aspiring AI Research Engineer | Focus: Computer Vision, Multimodal ML, Natural Language Processing*

---

### 🚀 About Me

I am a 5th-semester Computer Science student at IIITDM Kancheepuram (CGPA: 8.67) dedicated to advancing the state of the art in Artificial Intelligence. I am actively building a research portfolio aimed at top-tier MS programs and global R&D roles.

---

### 🧬 Selected Research & Projects

#### 📂 [Markerless Fast Bowling Analysis from a Single Side-On Video](https://github.com/Tarak-Ram-1908/fast-bowling-analysis)
*Reproducing elite-level cricket biomechanics from a phone camera instead of a motion-capture laboratory.*

Worthington's 2010 PhD thesis established the reference kinematics for elite fast bowling using eighteen Vicon cameras at 300 Hz, a floor-mounted Kistler force plate, and forty-seven reflective markers per bowler. Ten of his thirty elite subjects could not complete the protocol. This project asks whether the same measurements can be recovered from one side-on video shot at 120 fps, with no markers, no calibration object and no special equipment.

**I collected the dataset myself.** Two field sessions at IIITDM Kancheepuram produced **25 bowlers and 300+ deliveries**, filmed, organised, quality-audited and hand-labelled entirely by me — no public dataset exists for this problem. Every frame-level phase label, every event instant and every legality judgement in this repository is my own annotation.

The pipeline runs end to end: MediaPipe pose estimation → a per-frame delivery-phase classifier → event extraction for back foot contact, front foot contact and ball release → geometric computation of twelve joint angles and distances at those instants. Validation is leave-one-bowler-out throughout, never a random frame split, because adjacent frames 8 ms apart are near-duplicates and a random split reports an accuracy that means nothing.

Front knee angle at front foot contact measures **165.2° ± 8.4** against the thesis's elite **164.1° ± 6.1**, and plant angle **35.3° ± 4.7** against **36.3° ± 3.9** — agreement within a fifth of a standard deviation on measurements the original work needed a laboratory to obtain. Front foot contact is located within 3 frames on 89.7% of deliveries and ball release on 81.5%. Back foot contact remains weaker, and I traced that to label ambiguity rather than model capacity: five-fold and fifteen-fold cross-validation and two different model families all converge to the same number, which is the signature of an inconsistent target, not insufficient data.

Standing-height normalisation is derived from Winter's (1990) anthropometric trunk ratio, so stride length and release height are expressed as percentages of height without measuring a single bowler. 184 deliveries were reviewed frame by frame for bowling-action legality before any comparison against the published reference values, which describe legal actions only; this surfaced two bowlers whose every delivery was illegal.

*This is the project where I learned what data science actually costs. Holding a phone at the cr
