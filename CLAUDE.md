# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is GitHub's official collection of `.gitignore` file templates (https://github.com/github/gitignore). This is a **curated CONTENT repository**, not a traditional code repository - it contains no executable code, build systems, or test suites. The templates are used by GitHub.com's interface when users create new repositories and serve as a community reference for version control ignore patterns.

**Important:** There are no commands to build, test, or lint this repository. Quality control is entirely manual through maintainer review.

## Repository Structure (3-Tier Organization)

### Root Directory (157 templates)
- Mainstream language and framework templates with broad applicability
- Examples: Python.gitignore, Node.gitignore, Java.gitignore, Go.gitignore
- These are "evergreen" templates representing current versions

### Global/ (73 templates)
- Editor, OS, and tool-specific templates
- Meant to be added to user's global git configuration or merged into project templates
- Categories: Editors (JetBrains, VSCode, Vim, Emacs), OS (Windows, macOS, Linux), Tools (Docker, Terraform)
- **Key principle:** Environment-specific patterns belong here, not in language templates

### community/ (69+ templates in 15 subdirectories)
- Specialized templates for frameworks/tools not in mainstream use
- Versioned templates (older versions of frameworks live here)
- Organized by technology category: AWS/, DotNet/, Elixir/, Golang/, Java/, JavaScript/, etc.
- **Versioning strategy:** Root has current version, community/ has framework-v1.x.gitignore style names

## Template Conventions

### Standard Structure
Each .gitignore file follows consistent patterns:
- Header comments explaining the template (optional)
- Section comments grouping related patterns
- Cross-references to related templates
- Example from Python.gitignore:
  ```
  # PyCharm
  #   JetBrains specific template is maintained in a separate JetBrains.gitignore
  #   and can be added to the global gitignore or merged into this file.
  ```

### Common Sections
Templates typically organize patterns by:
- Build outputs (compiled files, binaries)
- Dependency directories
- Test coverage reports
- Logs and temporary files
- Environment files (.env)
- IDE-specific files (with reference to Global/)
- Framework-specific generated files
- Package manager artifacts

## Contributing Guidelines (CRITICAL)

These are strict requirements enforced by maintainers:

1. **ONE template per PR** - Do not modify multiple templates in a single PR
2. **Provide documentation links** - Link to official docs supporting the changes
3. **Explain broad applicability** - Changes must apply to everyone using that technology, not just specific edge cases
4. **Consider proper scope:**
   - Language-specific patterns → language template
   - Editor/IDE patterns → Global/ template
   - Framework patterns → appropriate framework template or community/
5. **For new templates:** Include link to project homepage
6. **Philosophy:** Curated collection of useful rules, NOT exhaustive file lists or brittle version-specific patterns

## Pull Request Process

1. Fork the repository
2. Create a branch for your changes
3. Modify the appropriate template(s) following guidelines above
4. Submit PR using the template in `.github/PULL_REQUEST_TEMPLATE.md`
5. Wait for review from @github/gitignore-maintainers (assigned via CODEOWNERS)

**Note:** PRs are automatically marked stale after 90 days of inactivity and closed after 180 days (via `.github/workflows/stale.yml`). Use 'keep' label to exempt from this automation.

## Key Architecture Insights

### Avoiding Duplication
Templates use cross-references rather than duplicating patterns. For example:
- Python.gitignore references JetBrains.gitignore for IDE patterns
- Language templates reference Global/ for editor-specific rules
- This keeps templates focused and maintainable

### When to Use Root vs Community
- **Root:** Current, widely-used technologies with broad adoption
- **community/:** Specialized frameworks, older versions, niche tools
- If uncertain, community/ is the safer starting point

### Template Categories in community/
- AWS/ - AWS-specific development tools
- DotNet/ - .NET framework variants
- Elixir/, Golang/, Java/, JavaScript/ - Language-specific frameworks
- embedded/ - Embedded systems development
- BoxLang/, CFML/, Linux/, GNOME/ - Platform/language specific

## License

All templates are released under CC0-1.0 (public domain dedication). No copyright restrictions apply.
