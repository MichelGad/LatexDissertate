# LatexDissertate 🎓✍️

## 🎯 Introduction

Ever found yourself lost in the labyrinth of academic formatting rules while trying to write your dissertation? Or perhaps you've struggled with maintaining consistency across chapters, figures, and tables? 🤔

LaTeX offers unparalleled control and professional typesetting, making it the gold standard for academic publications. However, setting up a robust, compliant, and easy-to-manage LaTeX project from scratch can be daunting, especially when juggling strict university guidelines for margins, spacing, and bibliography styles. 🤯

This project provides a comprehensive and highly customizable LaTeX template designed specifically for dissertations, bringing structure, clarity, and peace of mind to your writing process!

## 🚀 Project Goal: Streamlining dissertation Production

My goal is to offer a ready-to-use, academically compliant LaTeX template that simplifies the complex task of preparing a dissertation. It's built to be modular, easy to navigate, and pre-configured with essential packages and settings to meet common university requirements, allowing you to focus on your research, not the formatting!

## 🛠️ How It Works

This template leverages LaTeX's powerful document structuring capabilities to provide a clean and organized workflow:

1.  **Central Orchestration** 🧠
    The `dissertation.tex` file acts as the project's central hub. It loads all necessary packages, defines global settings, and explicitly includes all front matter, chapters, and back matter components in the correct order.

2.  **Modular Content Management** 📁
    Your dissertation content is neatly organized into dedicated subfolders (`frontmatter/`, `chapters/`, `endmatter/`). Each section or chapter resides in its own `.tex` file, making it easy to manage, edit, and collaborate on specific parts of your thesis. Smaller components (like sections within a chapter) can be further broken down using `\input{}`.

3.  **Configurable Metadata** ⚙️
    All your dissertation-specific information (title, author, university, supervisors, keywords) is defined in a single, dedicated file (`frontmatter/dissertation_metadata.tex`). Update it once, and it propagates throughout your document, including the custom title page and PDF metadata.

4.  **Academic Best Practices** ✨
    The template is pre-configured with industry-standard LaTeX packages for:
    *   **Page Layout**: Precise margins, headers, and footers with `geometry` and `fancyhdr`.
    *   **Line Spacing**: Easy control over single, 1.5, or double spacing with `setspace`.
    *   **Mathematics**: Beautifully typeset equations with `amsmath`, `amssymb`, `amsfonts`.
    *   **Figures & Tables**: Comprehensive tools for including graphics and creating professional tables with `graphicx`, `caption`, `booktabs`, `longtable`.
    *   **Bibliography**: Modern and flexible citation management using `biblatex` with `biber` backend.
    *   **Units & Numbers**: Correct typesetting of units and numbers (e.g., using decimal commas for German locale) with `siunitx`.
    *   **Glossary/Abbreviations**: Automated lists of acronyms and symbols with `glossaries-extra`.
    *   **Hyperlinks**: Clickable Table of Contents, citations, and internal links in your PDF with `hyperref`.

## ✨ Features

This template is packed with features to make your dissertation writing smoother:

### 1. Robust Document Structure
*   ✅ **Clear Separation**: Dedicated folders for `frontmatter`, `chapters`, and `endmatter` for superior organization.
*   ✅ **Modular Content Files**: Write each chapter and even major sections in its own `.tex` file, improving readability and maintenance.
*   ✅ **Numbered Chapters & Unnumbered Front Matter**: Correctly handles Roman numerals for front matter pages and Arabic numerals for main content, with chapters automatically numbered.

### 2. Academic & Formatting Compliance
*   📐 **Pre-set Margins**: Configured with common dissertation margin requirements.
*   📏 **Flexible Line Spacing**: Easily switch between `\doublespacing`, `\onehalfspacing`, or `\singlespacing`.
*   📜 **Automated Lists**: Generates Table of Contents, List of Figures, List of Tables, and List of Abbreviations automatically.
*   ✍️ **Custom Title Page**: A professional, customizable title page using your defined metadata and university logo.
*   📝 **Dedicated Environments**: Includes custom environments for your `Abstract` and `Acknowledgments`, formatted academically.

### 3. Advanced Features for Researchers
*   🔗 **Smart Referencing**: Seamless cross-referencing for chapters, sections, figures, tables, and equations using `\label` and `\ref`.
*   📚 **Modern Bibliography**: Uses `biblatex` with `biber` for advanced bibliography management, supporting various citation styles and precise control over entry details.
*   🔢 **Scientific Units & Numbers**: `siunitx` ensures consistent and correct typesetting of quantities, adhering to ISO standards and respecting locale-specific decimal markers (e.g., `,` for German).
*   🌐 **Interactive PDF**: Creates a fully hyperlinked PDF with clickable TOC entries, citations, and URLs, along with embedded document metadata.

**Current Stage:** This template is a comprehensive and ready-to-use LaTeX dissertation framework. ✅ All core features for structured writing, academic formatting, and robust compilation are implemented.

**Next Steps (for you!):**
*   Populate the `frontmatter/`, `chapters/`, and `endmatter/appendices/` files with your actual dissertation content.
*   Replace placeholder text (`\blindtext`) with your research.
*   Adjust the `\newcommand` values in `frontmatter/dissertation_metadata.tex` with your specific dissertation details.
*   Customize figure and table paths to point to your research data visualizations.
*   Consult your university's specific formatting guidelines and make any minor adjustments to the `geometry` or `fancyhdr` settings as needed.

## 🚀 Getting Started

Ready to write your dissertation with LaTeX? Follow these simple steps to set up your project locally.

### 1. Prerequisites

You'll need a LaTeX distribution installed on your system.
*   **TeX Live** (recommended for Linux/Windows)
*   **MiKTeX** (popular for Windows)
*   **MacTeX** (for macOS)

### 2. Clone the Repository

First, clone this GitHub repository to your local machine:

```
git clone https://github.com/MichelGad/LatexDissertate
```

### 3. Navigate to the Project Directory

Change into the newly cloned project directory:

```
cd LatexDissertate
```

### 4. Add Your University Logo

Place your university's logo (e.g.,`uni-logo.png` or `uni-logo.pdf`) directly in the ⁠`dissertation/ `root directory, or update the path in `⁠dissertation.tex` if you place it elsewhere (e.g., `⁠img/uni-logo.png`).

### 5. Compile the Document

To generate the final PDF and ensure all cross-references, bibliography, and glossaries are correctly built, you need to run a specific sequence of commands. Open your terminal (command prompt, PowerShell, or bash) in the ⁠`dissertation/` directory and execute these commands in order:

####	1.	First ⁠`pdflatex` run: 
Compiles the document, creates ⁠.aux files for cross-references, and ⁠.bcf for ⁠biber.
```
pdflatex dissertation.tex

```

####	2.	⁠`biber` run: 
Processes your ⁠`references.bib` file and generates the formatted bibliography.
```

biber dissertation

```

####	3.	⁠`makeglossaries` run: 
Creates your list of abbreviations/glossary.
```

makeglossaries dissertation
```


####	4.	Second `⁠pdflatex` run: 
Incorporates the bibliography and glossary, resolving citations and updating the Table of Contents.
```

pdflatex dissertation.tex
```


####	5.	Third ⁠`pdflatex` run (often needed): 

Ensures all internal references (page numbers for TOC/LOF/LOT/glossary, etc.) are completely stable.
```

pdflatex dissertation.tex
```


You are now ready to fill your dissertation with content! Your compiled PDF will be located at ⁠`dissertation.pdf` in the root directory. 🎉