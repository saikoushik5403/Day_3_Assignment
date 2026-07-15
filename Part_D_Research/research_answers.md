# Part D — Research Activities

This document contains answers and summaries for the five research activities in the CSS3 Fundamentals assignment (Section 28, Page 106).

---

### 1. Research CSS variables (custom properties like `--main-color: #333;`) and explain how they help maintainability.

*   **What they are**: CSS Variables (officially called **Custom Properties**) are developer-defined values that can be reused throughout a stylesheet. They are declared with a double-hyphen prefix (`--`) and accessed using the `var()` function.
    *   *Example*:
        ```css
        :root {
            --primary-color: #2563eb;
            --border-radius-base: 8px;
        }
        button {
            background-color: var(--primary-color);
            border-radius: var(--border-radius-base);
        }
        ```
*   **How they aid maintainability**:
    *   **Single Source of Truth**: If you need to change a brand color, typography scale, or padding unit across a massive stylesheet, you only need to update the variable declaration in one place (usually under the `:root` pseudo-class), and it updates everywhere instantly.
    *   **Readability**: Descriptive variable names (e.g., `--main-sidebar-bg`) explain the design intent of colors/dimensions far better than raw HEX codes or pixel values.
    *   **Dynamic Theming**: CSS variables can be modified dynamically at runtime using JavaScript (e.g., toggling between dark and light themes by swapping root variable values).

---

### 2. Research the BEM naming convention and write one example class name in BEM style.

*   **What it is**: **BEM** stands for **Block-Element-Modifier**. It is a popular front-end naming methodology designed to write modular, reusable, and self-documenting CSS classes in large-scale codebases.
*   **The Structure**:
    *   **`Block`**: A standalone entity that is meaningful on its own (e.g., `.card`, `.menu`, `.button`).
    *   **`Element`**: A part of the block that has no standalone meaning and is semantically tied to its block. Denoted by a **double underscore** `__` (e.g., `.card__title`, `.menu__item`).
    *   **`Modifier`**: A flag on a block or element used to change appearance, state, or behavior. Denoted by a **double hyphen** `--` (e.g., `.card--featured`, `.button--disabled`, `.menu__item--active`).
*   **Real-World Example**:
    A featured title inside a profile card:
    `class="profile-card__title--featured"`
    *   `profile-card` (Block)
    *   `title` (Element)
    *   `featured` (Modifier)

---

### 3. Look up three CSS pseudo-classes other than `:hover` (such as `:focus`, `:nth-child()`, `:first-child`) and describe what each does.

1.  **`:focus`**:
    *   *What it does*: Selects and styles an interactive element (like an input box, textarea, button, or link) at the exact moment it gains focus—meaning the user has clicked on it or navigated to it using the keyboard `Tab` key.
    *   *Real-world use*: Styling text input fields with a colored border shadow when active, which is essential for keyboard accessibility.
2.  **`:nth-child(n)`**:
    *   *What it does*: Matches an element based on its numerical position among its sibling elements. It can take numbers, formulas (like `2n+1`), or keywords (like `odd` or `even`).
    *   *Real-world use*: Creating "zebra-striped" rows in data tables (e.g., styling `tr:nth-child(even)` with a light gray background).
3.  **`:first-child`**:
    *   *What it does*: Targets an element only if it is the very first child element inside its parent container.
    *   *Real-world use*: Removing the top border or margin from the first paragraph in an article card, or removing the left padding from the first item in a horizontal menu list.

---

### 4. Research what Flexbox is and name three Flexbox properties (this prepares you for a later day).

*   **What it is**: **Flexbox** (Flexible Box Layout) is a one-dimensional CSS layout model designed for arranging items in a single direction—either horizontally in a row or vertically in a column. It makes it easy to align, distribute, and space items inside a container, even when their sizes are dynamic or unknown.
*   **Three Flexbox Properties**:
    1.  **`display: flex;`**: The trigger property set on the parent element (container) to initialize the flex formatting context.
    2.  **`justify-content`**: Aligns flex items along the **main axis** (e.g., horizontally by default). Common values include `center`, `space-between`, and `flex-end`.
    3.  **`flex-wrap`**: Controls whether the flex items are forced to stay on a single line (`nowrap`) or can wrap onto multiple lines (`wrap`) if they run out of container space.

---

### 5. Find a real website, open Developer Tools (F12), inspect an element, and identify three CSS properties applied to it and where they come from.

Inspecting the main sign-up CTA button on **GitHub** (https://github.com):

1.  **`display: inline-block;`**:
    *   *What it does*: Allows the button to sit inline with text/elements but respect padding and sizing.
    *   *Where it comes from*: The generic utility class `.btn` in GitHub's Primer CSS design system stylesheet.
2.  **`background-color: var(--button-primary-bgColor-rest);`**:
    *   *What it does*: Sets the primary green background color of the CTA button.
    *   *Where it comes from*: Defined inside a specific theme ruleset (e.g., `.btn-primary` combined with light/dark theme attributes) referencing a CSS color variable.
3.  **`border-radius: 6px;`**:
    *   *What it does*: Creates modern, slightly rounded corners for the button.
    *   *Where it comes from*: Part of the standard button styling block in the global production stylesheet.
