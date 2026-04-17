# ERROR DOCUMENTATION

## index.html

### Error 1
Line 70: Link cards use div instead of anchor tags.
What went wrong: Cards have no href, clicking does nothing.
What should be: Use <a> tags with href attributes or add onclick handlers.
Why sloppy: Copy-paste from CSS template without checking interactivity.
What missed: Navigation structure needs HTML semantics.
How to prevent: Test all clickable elements before deploying.

### Error 2
Line 58: Code block shows console.log without proper HTML escape.
What went wrong: Special characters in code could break rendering.
What should be: Use <pre><code> tags with proper escaping or use textContent.
Why sloppy: Hardcoded string without checking for < > & characters.
What missed: Code display needs character escaping.
How to prevent: Always escape user content in HTML.

### Error 3
Line 23: Absolute positioning units used (40px, 20px).
What went wrong: Not responsive on very small screens (< 320px width).
What should be: Use relative units or media queries for screens < 400px.
Why sloppy: Desktop-first design without mobile consideration.
What missed: Testing on actual mobile devices.
How to prevent: Test on real devices, not just browser zoom.

## hello-world/index.html

### Error 4
Line 2: Hard-coded publication date "April 17, 2024".
What went wrong: Date is static, becomes stale.
What should be: Use current date or make it template variable.
Why sloppy: Manual date entry assumes no future edits.
What missed: Dynamic content requirements.
How to prevent: Use build tool to inject dates automatically.

### Error 5
Line 65: Code block shows multi-language examples but no language labels.
What went wrong: Reader cannot identify which language is which.
What should be: Add comments or separate sections with language names.
Why sloppy: Assumed visual separation is enough.
What missed: Accessibility for code blocks.
How to prevent: Add explicit labels to every code block.

## README.md

### Error 6
Line 1: Claims "comprehensive guide" but only has 1 blog post.
What went wrong: Overpromises content.
What should be: Say "Introduction to string algorithms" not "comprehensive".
Why sloppy: Written before content exists.
What missed: Content scope reality check.
How to prevent: Only write descriptions after content is complete.

### Error 7
Line 26: URL points to GitHub Pages but GitHub Pages not configured.
What went wrong: Link returns 404 when deployed.
What should be: Remove link until GitHub Pages is actually enabled.
Why sloppy: Assumed GitHub Pages would work without configuration.
What missed: Repository settings configuration step.
How to prevent: Configure GitHub Pages in repo settings before deploying.

## _config.yml

### Error 8
Line 3: baseurl is /string_algorithms but index.html links are absolute.
What went wrong: Links break if site deployed under different baseurl.
What should be: Use Jekyll liquid tags {{ site.baseurl }}/path or consistent relative paths.
Why sloppy: Jekyll config exists but HTML does not use it.
What missed: Understanding Jekyll vs static HTML.
How to prevent: Use either full Jekyll or full static HTML, not mixed.

## General Project Issues

### Error 9
Line structure: No file extension consistency check.
What went wrong: .html files exist but .md files not processed as pages.
What should be: Use Jekyll post structure in _posts/ directory or convert to Jekyll.
Why sloppy: Created config.yml but site structure does not follow it.
What missed: Jekyll directory structure requirements.
How to prevent: Review tool documentation before creating config files.

### Error 10
Line repository: No test file exists.
What went wrong: Cannot verify HTML validity before deployment.
What should be: Add test script or use CI to validate HTML.
Why sloppy: No quality gate before commit.
What missed: Testing process definition.
How to prevent: Write tests before writing code.

### Error 11
Line git: All files added in single commit without modular structure.
What went wrong: Cannot revert individual features.
What should be: Separate commits: setup, blog-post, config, docs.
Why sloppy: Added all at once without staging strategy.
What missed: Commit granularity principles.
How to prevent: Commit after each logical unit of work.

### Error 12
Line branch: No main/master branch exists.
What went wrong: Cannot create pull request.
What should be: Create main branch first, then feature branches.
Why sloppy: Developed on feature branch without base.
What missed: Git workflow setup.
How to prevent: Initialize repo with main branch before feature work.

## Items to Fix Before Merge

1. Create main branch
2. Test HTML files in browser
3. Configure GitHub Pages in repository settings
4. Update README.md to remove premature claims
5. Add language labels to code blocks
6. Remove hardcoded dates or make them dynamic
7. Make link cards functional
8. Add commit-per-feature history
