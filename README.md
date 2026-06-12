Here is the raw Markdown directly in the chat, exactly as requested. No canvas, no guessing.

```markdown
# SyntaxStack

A single-file, zero-dependency JavaScript application for generating randomized, weighted text strings from custom data sets. It is built to be easily modified for any specific use case by swapping out the underlying arrays and template logic. 

Everything runs locally in the browser. 

## Features

* **No Dependencies:** Runs entirely client-side. No backend, APIs, or external libraries required.
* **Customizable Data:** Swap out the placeholder arrays to generate anything from code snippets to meal plans or technical documentation.
* **Mobile Responsive:** Layout adapts to desktop, tablet, and mobile screens.
* **File Parsing:** Users can upload custom `.txt` or `.perchance` files to override the built-in generation rules.
* **Audio Feedback:** Simple UI sound effects for user interactions.
* **Syntax Highlighting:** Output text is color-coded based on customizable regular expressions.

## How to Customize

To modify this template for your specific project, update the placeholder values in `index.html`.

### 1. UI Elements

Search the HTML file for `[PLACEHOLDER]` tags to update the visible text. This includes the browser tab, main headers, column titles, and button labels.

### 2. Global Arrays

Locate the `LEXICON.universal` object in the JavaScript. This section holds arrays of data that apply across all your categories. Replace `[GLOBAL_1A]`, `[GLOBAL_1B]`, etc., with your actual data points.

### 3. Categories

Locate the `LEXICON.domains` object. These act as the main selectable options on the left sidebar. 
* Change the `name` and `desc` for the UI buttons.
* Replace the `primary_element`, `secondary_element`, etc., arrays with data specific to that category.

### 4. Template Logic

The `buildPresetFromDomain` function controls how your data is assembled into the final output string.
* Update the `template` strings to format how the selected words combine. 
* Bracket notation (e.g., `[primary_element]`) pulls a random item from that specific array.
* The `{w}` markers allow the user to apply numerical weights to that specific section via the UI.

### 5. Syntax Highlighting

To keep the color-coded output working with your new templates, update the `UI.highlightTokens` function at the bottom of the script. Adjust the regular expressions (`.replace()`) to match the exact text prefixes you set up in your template logic.

## File Structure

```text
/
└── index.html  # Contains all HTML, CSS, and JavaScript

```

## Getting Started

1. Clone or download this repository.
2. Open `index.html` in a text editor.
3. Replace the placeholder arrays and UI strings with your target data.
4. Open the file in any web browser to run the application.

## Custom File Upload Format

Users can upload their own text files to generate strings using pipe-delimited syntax. Here is a basic example of the supported format:

```text
subject = Knight | Wizard ^ 2.5 | Rogue
weapon = Sword | Staff | Dagger
output = The [subject] attacks with a [weapon]!

```
