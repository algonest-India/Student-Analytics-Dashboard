### Step-by-Step Instructions: Creating the CSS Styles for Your Student Dashboard Capstone Project

As part of your capstone project, you'll build the `dashboard.css` file from scratch to style the dashboard layout using CSS Grid. This guide walks you through the process section by section, explaining key concepts like resets, grid setup, and responsive design. Follow along by typing the code into a new file called `dashboard.css`, and test it frequently by opening `index.html` in your browser (link the CSS in the HTML `<head>` with `<link rel="stylesheet" href="./css/dashboard.css">`).

**Prerequisites**: 
- You have the `index.html` file ready (from the previous step).
- Use a code editor like VS Code for syntax highlighting.
- Refresh the browser after each major section to see changes.

#### Step 1: Set Up the CSS Reset and Base Styles
Start with a clean slate to avoid browser defaults interfering with your grid.

- Open `dashboard.css` and add the universal reset:

  - **Why?** `margin: 0; padding: 0;` removes default spacing. `box-sizing: border-box;` ensures padding/borders don't add to element widths.

- Add body styles for typography and background:
 
  - **Why?** Sets a modern font stack (fallbacks included), readable line height, dark text, and light gray background for contrast.

**Test**: Save and refresh—your HTML should now have consistent text without extra margins.

#### Step 2: Define the Main Grid Container
Use CSS Grid to structure the overall page: header (top, full-width), sidebar (left, fixed), main (right, flexible), footer (bottom, full-width).

- Add the grid container rules:
  
  - **Why?** `display: grid;` enables Grid. `grid-template-columns` uses `fr` (fraction) for responsive main area. `grid-template-areas` names regions for easy placement (like a blueprint). `min-height: 100vh` fills the viewport.

**Test**: Your layout should now have the header spanning top, sidebar on left, main on right, and footer at bottom. Content might look unstyled— that's next!

#### Step 3: Style the Header (Navigation Bar)
Make the header visually appealing with a gradient and flexbox for layout.

- Add header styles:
  
  - **Why?** `grid-area: header;` places it in the named area (spans both columns). `linear-gradient` adds a purple-blue fade. `flex` with `justify-content: space-between` pushes title and nav apart. `transition` smooths hover effects.

**Test**: Header should be colorful, with nav links on the right. Hover to see fade.

#### Step 4: Style the Sidebar (Quick Links)
Create a dark, vertical menu.

- Add sidebar styles:
  
  - **Why?** `grid-area: sidebar;` fixes it to the left column. Dark navy background for contrast. `display: block;` on links makes them full-width buttons. Hover changes background for interactivity.

**Test**: Sidebar should be dark with white text; links highlight on hover.

#### Step 5: Style the Main Content (Stats and Chart)
Focus on the main area: sections for stats (grid of cards) and a chart placeholder.

- First, main container:
  
  - **Why?** `grid-area: main;` places it in the flexible column. White background for content focus. `overflow-y: auto;` allows scrolling if needed.

- Now, stats grid (cards):
  
  - **Why?** Nested grid with `repeat(auto-fit, minmax(200px, 1fr))` creates responsive cards (at least 200px wide, flexible). Classes like `.positive` use semantic colors for changes. Hover lift adds polish.

- Chart placeholder:
  
  - **Why?** Dashed border signals "placeholder." Flex centers content vertically/horizontally.

**Test**: Main should show white cards with stats (green/orange/red accents) and a gray chart box.

#### Step 6: Style the Footer
Simple bottom bar.

- Add footer:
  
  - **Why?** `grid-area: footer;` spans bottom. Dark background matches sidebar theme.

**Test**: Footer at bottom with centered text.

#### Step 7: Add Responsive Design with Media Queries
Ensure it works on mobile—stack elements vertically.

- Add at the end:
  
  - **Why?** `@media` targets screen widths. On tablets (768px), stack with `grid-template-areas` and `order: 3` (reorders sidebar below main). On phones (480px), single-column cards. `flex-direction: column` stacks header elements.

**Test**: Resize browser or use DevTools (Ctrl+Shift+M in Chrome) to simulate mobile—layout should adapt without breaking.

#### Final Tips for Your Capstone
- **Debugging**: Use browser DevTools > Elements tab to inspect grids (enable "CSS Grid" overlay). Check for errors in console.
- **Customization Ideas**:
  - Add dark mode: Use `@media (prefers-color-scheme: dark)` to invert colors.
  - Animations: Enhance cards with `@keyframes` for fade-ins.
  - Accessibility: Add `focus` styles for keyboard nav (e.g., `a:focus { outline: 2px solid #667eea; }`).
- **Best Practices**: Keep code modular (one rule per logical group). Comment complex parts (e.g., `/* Responsive stack */`).
- **Next Steps**: Integrate JavaScript for dynamic stats (e.g., fetch API data). Deploy to Netlify or GitHub Pages.

You've now built a professional dashboard CSS! Compare your file to the reference—if it matches, great job. Questions or want to add features? Experiment and share your version.
```