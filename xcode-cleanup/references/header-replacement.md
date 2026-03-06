# Header Replacement Patterns

## Default Xcode Header Format

```swift
//
//  FileName.swift
//  ProjectName
//
//  Created by Author Name on Date.
//
```

This is typically 6-7 lines that should be detected and replaced.

## Minimal Template Format

```swift
// FileName.swift
```

Just a single-line comment with the filename. That's it.

## Replacement Strategy

1. Find the block of comment lines at the top of each file
2. Match pattern: starts with `//`, contains filename, contains "Created by", ends with `//`
3. Extract just the filename from the second line
4. Replace entire block with `// FileName.swift`
5. Preserve any blank lines that follow the header

## Important Notes

- The first line after replacement must start with `// ` (comment format)
- Keep one blank line after the header before imports
- Don't modify any code, only the top file header
- Be careful with multi-line string literals that might contain comment-like content
