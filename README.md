# Salesforce Formula Editor

A simple web-based utility to visually edit and build Salesforce formulas. This tool parses a Salesforce formula string into an interactive tree of inputs and operators, allowing for easier modification and understanding of complex nested logic. The edited structure can then be converted back into a Salesforce formula string.

## Features

*   **Visual Representation:** Displays nested formulas in an easy-to-understand tree structure.
*   **Interactive Editing:** Modify field names, literal values, and operators directly in the UI.
*   **Dynamic Structure:** Add or Remove conditions and arguments within logical functions like `AND`/`OR`.
*   **Formula Regeneration:** Rebuild the Salesforce formula string from the current state of the UI.
*   **Basic Syntax Validation:** Pre-checks the input formula for common issues like mismatched parentheses and missing arguments, highlighting the error location in the input.
*   **No Backend Needed:** Runs entirely in the browser using HTML, CSS, and JavaScript.

## Screenshots

## Setup / Usage

1.  **Download:** Clone the repository or download the `index.html` file (or the file containing the code).
2.  **Open:** Open the HTML file directly in your web browser. No web server is required.

**How to Use:**

1.  **Input Formula:** Paste your existing Salesforce formula into the "Input Formula" text area, or type a new one.
2.  **Parse:** Click the "Parse Formula" button.
    *   If there are syntax errors, messages will appear, and the approximate error location will be highlighted in the input area.
    *   If successful, the "Formula Editor UI" section will populate.
3.  **Edit:** Interact with the generated UI:
    *   Modify text inputs for field names and literal values.
    *   Change operators using the dropdowns.
    *   Click "X" (Remove) buttons to delete parts of the formula.
    *   Click "Add Argument" buttons within functions like `AND` to add new conditions.
4.  **Generate:** Click the "Generate Formula String" button. The "Generated Formula" text area will update with the string representation of the current UI state.
5.  **Copy:** Copy the formula from the "Generated Formula" text area to use in Salesforce.

## Diagram - Workflow

This is a conceptual flow of how the editor works:

```mermaid
graph TD
    A[Input Formula String] --> B{Validate Syntax};
    B -- Valid --> C{Parse Formula};
    C --> D[Render Interactive UI];
    D --> E{User Edits UI};
    E --> F[Generate Formula String];
    F --> G[Output Formula String];
    B -- Invalid --> H[Show Errors & Highlight];
