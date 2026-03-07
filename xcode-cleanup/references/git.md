# Git Configuration

Essential git configuration files for Xcode projects. These templates help manage source control properly and ensure consistent file handling across platforms.

## Purpose

- **`.gitignore`** - Prevents committing build artifacts, user data, and platform-specific files that should not be in version control
- **`.gitattributes`** - Defines how git handles different file types (text vs binary), ensuring consistent line endings across Windows, macOS, and Linux

## Files to Create

### .gitignore

Prevents Xcode-specific files and build artifacts from being committed:

```
.DS_Store
build/
.build/
xcuserdata/
```

**What this ignores:**
- `.DS_Store` - macOS folder metadata (not needed in repo)
- `build/` - Build output directory (regenerated on each build)
- `.build/` - Alternative build directory for Swift Package Manager
- `xcuserdata/` - Xcode user settings and breakpoints (personal to each developer)

### .gitattributes

Defines file type handling and line ending normalization:

```
*.sh text
*.swift text
*.py text
*.md text
*.pdf binary
*.jpg binary
*.jpeg binary
*.png binary
```

**What this does:**
- `text` - Automatically normalizes line endings (CRLF on Windows → LF on Unix)
- `binary` - Treats files as binary; git won't attempt line ending conversion
- Text files like `.sh`, `.swift`, `.py`, `.md` should have consistent line endings across all platforms
- Binary files like images and PDFs should never be modified by git's line ending logic

## When to Add

Create these files when:
1. Starting a new Xcode project that will be shared with others
2. Setting up version control for the first time
3. Cleaning up an existing project to establish standards

## Integration with xcode-cleanup

These files work alongside the main `xcode-cleanup` skill which handles:
- Setting minimal file headers
- Removing metadata from source files
- Configuring Xcode templates

Git configuration ensures proper version control practices while the skill ensures clean, minimal file headers.
