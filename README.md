# 🧬 Sequence Alignment Visualizer

A lightweight, browser-based visualizer for demonstrating DNA sequence homology, mapping primer hybridization, and discovering conserved regions.

Built for researchers and bioinformaticians, this tool runs entirely in your browser. It eliminates the need for clunky text-editor alignments by mathematically locking sequences to a strict CSS grid, ensuring flawless formatting for publication-ready exports.

## ⚠️ Scientific Disclaimer: Visualization vs. Computation
Please note that this tool is strictly an **alignment visualizer and annotation tool**. It does **not** perform algorithmic multi-sequence alignment (MSA) in the background (e.g., it does not use MUSCLE, Clustal, or Needleman-Wunsch). It assumes the sequences you input are already pre-aligned or highly homologous. Its primary purpose is to visually map primer hybridization and highlight identical bases across the sequences provided, not to solve mathematical alignment problems.

## ✨ Key Features

* **Multi-Sequence Visualization:** Compare an unlimited number of species sequences simultaneously. Automatically formats into human-readable 100bp chunks with precise coordinate rulers.
* **Smart Primer Hybridization:** * Add Forward and Reverse primers with intelligent orientation logic.
  * Define targets using rigorous nomenclature (Target: Coding Strand vs. Target: Template Strand).
  * Auto-calculates 5' ➔ 3' lab order sequences, even from visual or copied alignments.
* **Conserved Region Discovery:** Actively scan alignments to highlight unbroken runs of identical nucleotides across all species (filter by exact, minimum, or maximum base-pair lengths).
* **Smart Copy & Paste:** Copy directly from the visual grid; a custom clipboard interceptor automatically strips spaces and rulers, yielding pure DNA strings.
* **Publication-Ready Export:** One-click, high-definition PNG rendering of your alignment maps for immediate use in presentations and lab notebooks.

## 🚀 Usage

Because the Visualizer is a pure client-side application, no installation or backend server is required. 

**Local Execution:**
1. Clone this repository or download the `index.html` file.
2. Double-click `index.html` to open it in any modern web browser (Chrome, Safari, Firefox, Edge).
3. Paste your target DNA sequences, configure your primers, and click the camera icon to export.

## 🛠️ Tech Stack

* **HTML5 / CSS3:** Utilizing CSS Grid architectures for pixel-perfect sequence locking.
* **Vanilla JavaScript (ES6):** Handles all string manipulation, reverse-complement logic, and DOM rendering natively.
* **html2canvas:** Third-party library utilized for HD DOM-to-Image capture.

## ⚠️ Known Limitations (Current Version)
As this visualizer is actively being developed, there are a few known UI/UX quirks in the current build:
* **Primer Overlap Rendering:** If multiple primers heavily overlap on the exact same sequence chunk, their name tags and vertical guide lines may occasionally clip or visually overlap. 
* **PNG Export Chevron Bug:** The `html2canvas` screenshot engine currently does not support CSS `clip-path` properties. While the primers display as directional arrows (chevrons) in the live browser, they will render as standard rectangles in the downloaded `.png` image. 

## 🗺️ Roadmap & Future Features
We are continuously working to upgrade the Visualizer. Planned features for upcoming releases include:
* **RNA Support:** Implementation of RNA sequence handling, including automated Thymine/Uracil (T/U) toggling for transcript alignments.
* **SVG/Canvas Engine Upgrade:** Rebuilding the primer rendering engine to ensure directional arrows are perfectly preserved during image export.
* **Dynamic Collision Detection:** Upgrading the primer track engine to stack overlapping primer names seamlessly without visual clipping.
