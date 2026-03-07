---
name: xcode-cleanup
description: Cleanup newly created Xcode projects by setting minimal headers and removing metadata from source files.
license: MIT
metadata:
  author: Brennan Stehling
  version: "1.0"
---

Automate cleanup of newly created Xcode projects to remove personal metadata and establish minimal, clean file headers.

## Process

1. Check if this is an Xcode project by looking for `*.xcodeproj` directory.
2. Create `.gitignore` and `.gitattributes` files in the project root using templates from `references/git.md`.
3. Create `.xcodeproj/xcshareddata/IDETemplateMacros.plist` with minimal header template using `references/template-macros.xml`.
4. Find all Swift source files in the project using patterns from `references/file-patterns.md`.
5. Replace all default Xcode headers with minimal format using patterns from `references/header-replacement.md`.
6. Verify changes were applied correctly.

## Core Instructions

- This skill runs on newly created Xcode projects where cleanup hasn't been done yet.
- It preserves all code - only modifies file headers and configuration.
- It works on all Swift file targets: main app, tests, UI tests, and any other bundles.
- The minimal header format is: `// FileName.swift` (just filename comment, nothing else).
- Privacy-first approach: removes creator names, dates, and other metadata.

## Output Format

Report what was done:
1. Whether git configuration files (`.gitignore`, `.gitattributes`) were created or already existed
2. Whether `IDETemplateMacros.plist` was created or already existed
3. How many Swift files were found
4. How many headers were successfully replaced
5. Any files that couldn't be processed

Example output:
```
✅ Created .gitignore for Xcode projects
✅ Created .gitattributes for consistent file handling
✅ Created IDETemplateMacros.plist for minimal headers
📝 Found 5 Swift files
✏️  Updated 5 file headers to minimal format:
  - FlaschenTaschenApp.swift
  - ContentView.swift
  - FlaschenTaschenTests.swift
  - FlaschenTaschenUITests.swift
  - FlaschenTaschenUITestsLaunchTests.swift
```

## References

- `references/git.md` - Git configuration templates (.gitignore and .gitattributes)
- `references/template-macros.xml` - The IDETemplateMacros.plist configuration file content
- `references/file-patterns.md` - Patterns to find Swift source files
- `references/header-replacement.md` - Header replacement patterns and format
