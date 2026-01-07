# Copilot / AI agent instructions for LeetProblem

Short summary
- Small repo of standalone LeetCode-style solutions. Each solution lives in its own HTML file and contains a <script> tag with a self-contained JavaScript implementation and an example input that is printed with `console.log`.

How to run and verify changes ✅
- Fastest manual check: open the HTML file in a browser and inspect the Console (DevTools) to see the example outputs.
- Run in Node (recommended for automated checks): copy the contents of the `<script>` into a `.js` file (e.g., `add_two_numbers.js`) and run `node add_two_numbers.js`.
  - Example: copy the `ListNode` class, test input creation, and `console.log(addTwoNumbers(...))` from `add_two_numbers.html` into `add_two_numbers.js` then run `node add_two_numbers.js`.
- There is no test harness or package.json in the repo currently; add tests as standalone `.js` test files if needed and document how to run them in the PR.

Repository patterns & conventions (discoverable) 🔍
- File layout: each solved problem is a single HTML file with an inline `<script>` block containing the solution, sample input construction, and a `console.log` showing the result (see `add_two_numbers.html`, `longestSubstring.html`).
- Data setup: test inputs are constructed inline (e.g., `ListNode` chains are created manually in `add_two_numbers.html`).
- API style: solutions target small standalone functions (e.g., `addTwoNumbers`, `lengthOfLongestSubstring`) and often define helper classes (e.g., `ListNode`).
- Output: interactive/debug output is via `console.log` only; no structured test output is present.
- Naming: filenames demonstrate two styles (snake_case `add_two_numbers.html` and camelCase `longestSubstring.html`). Maintain consistency when adding new files and mention the choice in your PR.

Common issues to watch for (concrete, repo-specific) ⚠️
- `longestSubstring.html` contains observable bugs (use of `seen` as a string while calling Set methods `.has`/`.add`, undefined `s` variable, and `console.log(d())` at the end). Always run the file to reproduce errors before changing logic.
- Because code is embedded in HTML, missing or wrong variable names can be masked unless executed; prefer extracting to `.js` for step-by-step debugging.

PR guidelines and expectations 🔧
- Keep the solution self-contained and include a small, reproducible example using `console.log` (mirrors existing files).
- When fixing a bug, include a short note in the PR description explaining how you reproduced the failing behavior (browser console or `node`) and why the fix is correct.
- If you introduce a test harness, add clear instructions in the README and include simple npm scripts (e.g., `npm test`) in a future addition.

Search & navigation tips 💡
- Grep for function names (e.g., `addTwoNumbers`, `lengthOfLongestSubstring`) to find related files quickly.
- Use the browser console for quick iteration; extract code to `.js` for step-through debugging with Node debuggers or editor breakpoints.

If anything is unclear or missing from this guidance, tell me which part you'd like expanded (examples, test conventions, or PR templates) and I'll iterate. ✅