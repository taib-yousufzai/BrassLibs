# Design Document: Brand Name Standardization

## Overview

This design outlines the approach for standardizing the company name "Brass Space Interior" across three separate React-based applications: the quotation system, photo library system, and mood board builder. The standardization involves updating UI components, configuration files, code comments, and documentation to ensure consistent branding throughout all customer-facing and internal touchpoints.

The implementation will be a straightforward find-and-replace operation across multiple files, with careful attention to context-specific usage (full name vs. extended name vs. package naming conventions). No architectural changes are required, as this is purely a content standardization effort.

## Architecture

### System Context

The three applications are independent React projects:

1. **Quotation System** (`quotation/quotation/quotation/`)
   - React application for generating and viewing quotations
   - Uses Firebase for backend services
   - Contains UI components that display company information

2. **Library System** (`library (2)/library/Photolibrary/`)
   - React application for photo library management
   - Uses Firebase authentication and storage
   - Contains admin and user registration flows

3. **Mood Board System** (`mood_board-builder/`)
   - React application for creating mood boards
   - Uses Zustand for state management
   - Contains auto-generator functionality with company references

### Standardization Strategy

The standardization will follow these principles:

1. **User-Facing Content**: Use "Brass Space Interior" as the primary brand name
2. **Extended Branding**: Use "Brass Space Interior Solution" where a fuller description is appropriate
3. **Package Names**: Use "brass-space-interior" in kebab-case for package.json
4. **Code Comments**: Use "Brass Space Interior" for consistency
5. **Domain References**: Keep "brassspace.com" but ensure context includes full brand name

## Components and Interfaces

### Quotation System Components

#### Header Component (`src/components/Header.jsx`)
- **Current State**: Displays "Brass Space"
- **Required Change**: Update to "Brass Space Interior"
- **Location**: Company name display in header navigation

#### QuotePreview Component (`src/components/QuotePreview.jsx`)
- **Current State**: Multiple instances of "Brass Space"
- **Required Changes**:
  - Company information section: "Brass Space Interior"
  - Bank details section: "Brass Space Interior"
  - Signature section: "Brass Space Interior"
  - Footer section: "Brass Space Interior"

#### ViewQuotation Page (`src/pages/ViewQuotation.jsx`)
- **Current State**: Multiple instances of "Brass Space"
- **Required Changes**:
  - Company information section: "Brass Space Interior"
  - Bank details section: "Brass Space Interior"
  - Signature section: "Brass Space Interior"
  - Footer section: "Brass Space Interior"

#### Firebase Configuration (`src/firebase.js`)
- **Current State**: Comment references "Brass Space"
- **Required Change**: Update comment to "Brass Space Interior"

#### Package Configuration (`package.json`)
- **Current State**: "brass-space-quotation-builder"
- **Required Change**: "brass-space-interior-quotation-builder"

### Library System Components

#### LocalAuthContext (`src/context/LocalAuthContext.jsx`)
- **Current State**: May contain admin email references
- **Required Change**: Ensure any company references use "Brass Space Interior"

#### Register Page (`src/pages/Register.jsx`)
- **Current State**: May contain company references in registration flow
- **Required Change**: Update to "Brass Space Interior"

#### Role Manager Utility (`src/utils/roleManager.js`)
- **Current State**: May contain admin role references
- **Required Change**: Update any company references to "Brass Space Interior Admin"

#### Package Configuration (`package.json`)
- **Current State**: Needs verification
- **Required Change**: Ensure uses "brass-space-interior" pattern if applicable

### Mood Board System Components

#### Auto Generator Store (`src/store/autoGeneratorStore.js`)
- **Current State**: Uses "Brass Space Interior Solution" (correct)
- **Required Change**: Verify consistency, update email/website context if needed

#### Package Configuration (`package.json`)
- **Current State**: Needs verification
- **Required Change**: Ensure uses "brass-space-interior" pattern if applicable

## Data Models

No data model changes are required. This is a content standardization effort that does not affect data structures, database schemas, or API contracts.

### String Replacement Patterns

The following patterns will be used for replacements:

```
Pattern 1: User-Facing Display Names
Old: "Brass Space"
New: "Brass Space Interior"
Context: UI components, headers, footers, signatures

Pattern 2: Extended Branding
Old: "Brass Space Interior Solution" (keep as-is where already used)
New: "Brass Space Interior Solution" (use in appropriate contexts)
Context: Full company descriptions

Pattern 3: Package Names
Old: "brass-space-*"
New: "brass-space-interior-*"
Context: package.json files

Pattern 4: Code Comments
Old: "Brass Space"
New: "Brass Space Interior"
Context: JavaScript/JSX comments

Pattern 5: Domain Context
Old: "brassspace.com" (standalone)
New: "brassspace.com" with "Brass Space Interior" context
Context: Email and website references
```


## Correctness Properties

*A property is a characteristic or behavior that should hold true across all valid executions of a system—essentially, a formal statement about what the system should do. Properties serve as the bridge between human-readable specifications and machine-verifiable correctness guarantees.*

### Property 1: User-Facing Content Consistency

*For any* user-facing file (React components, pages, UI elements) across all three projects, all instances of the company name should be "Brass Space Interior" or "Brass Space Interior Solution", and no instance of "Brass Space" alone should exist in rendered content.

**Validates: Requirements 1.1, 1.3, 1.4, 2.1, 2.2, 2.3, 2.4, 2.5, 3.2, 3.3, 4.1, 4.2**

### Property 2: Package Name Consistency

*For any* package.json file across all three projects, the package name should follow the pattern "brass-space-interior" or "brass-space-interior-[project-name]", and should not use abbreviated forms like "brass-space".

**Validates: Requirements 5.1, 5.2, 5.3**

### Property 3: Code Comments and Documentation Consistency

*For any* code comment or documentation file across all three projects, all references to the company should use "Brass Space Interior" or "Brass Space Interior Solution", and should not use "Brass Space" alone.

**Validates: Requirements 6.1, 6.2, 6.3**

## Error Handling

This standardization effort has minimal error handling requirements since it involves static content updates. However, the following considerations apply:

### Validation Checks

1. **Pre-Update Verification**: Before making changes, verify that target files exist and are accessible
2. **Syntax Preservation**: Ensure that string replacements maintain valid JavaScript/JSX syntax
3. **Context Awareness**: Verify that replacements don't inadvertently change unrelated strings (e.g., URLs, technical terms)

### Rollback Strategy

1. **Version Control**: All changes should be committed to version control with clear commit messages
2. **Atomic Changes**: Changes should be made per project to allow for easy rollback if issues arise
3. **Testing**: Each project should be tested after changes to ensure no runtime errors were introduced

### Edge Cases

1. **Concatenated Strings**: Handle cases where "Brass Space" might be split across multiple string concatenations
2. **Template Literals**: Ensure replacements work correctly within template literals
3. **JSX Attributes**: Verify replacements in JSX attribute values maintain proper quoting
4. **Comments**: Handle both single-line (//) and multi-line (/* */) comment formats

## Testing Strategy

This feature requires a dual testing approach combining automated validation with manual verification.

### Unit Tests

Unit tests will focus on specific examples and verification of individual files:

1. **Component Rendering Tests**: Verify that specific components render the correct company name
   - Test Header component displays "Brass Space Interior"
   - Test QuotePreview component displays "Brass Space Interior" in all sections
   - Test ViewQuotation page displays "Brass Space Interior" in all sections
   - Test admin references in Library system use "Brass Space Interior Admin"

2. **Configuration Tests**: Verify package.json files contain correct naming
   - Test quotation package.json uses "brass-space-interior-quotation-builder"
   - Test library package.json uses correct pattern
   - Test mood board package.json uses correct pattern

3. **Edge Case Tests**: Verify handling of special cases
   - Test that domain references (brassspace.com) are preserved
   - Test that replacements don't affect unrelated strings
   - Test that JSX syntax remains valid after replacements

### Property-Based Tests

Property-based tests will verify universal correctness across all files. Each test should run a minimum of 100 iterations.

1. **Property Test 1: User-Facing Content Consistency**
   - **Feature: brand-name-standardization, Property 1: For any user-facing file across all three projects, all instances of the company name should be "Brass Space Interior" or "Brass Space Interior Solution"**
   - Generate: List of all React component files (.jsx, .js files in src/components, src/pages)
   - Test: Parse each file and verify no standalone "Brass Space" exists in JSX content
   - Verify: All company name references use full form

2. **Property Test 2: Package Name Consistency**
   - **Feature: brand-name-standardization, Property 2: For any package.json file, the package name should follow the pattern "brass-space-interior" or "brass-space-interior-[project-name]"**
   - Generate: List of all package.json files across projects
   - Test: Parse each package.json and extract "name" field
   - Verify: Name matches pattern and doesn't use abbreviated form

3. **Property Test 3: Code Comments and Documentation Consistency**
   - **Feature: brand-name-standardization, Property 3: For any code comment or documentation file, all references to the company should use "Brass Space Interior" or "Brass Space Interior Solution"**
   - Generate: List of all source files and markdown documentation
   - Test: Extract all comments and search for company references
   - Verify: All references use full company name

### Testing Library Selection

For JavaScript/React projects, we will use:
- **Jest**: For unit tests and component rendering tests
- **fast-check**: For property-based testing with configurable iteration counts
- **@testing-library/react**: For component testing utilities

### Manual Verification

After automated tests pass, manual verification should include:

1. **Visual Inspection**: Run each application and visually verify company name displays correctly
2. **Quote Generation**: Generate a sample quotation and verify all sections show correct name
3. **Registration Flow**: Test library registration flow to verify branding
4. **Mood Board Creation**: Create a mood board and verify company references

### Test Configuration

All property-based tests must be configured with:
- Minimum 100 iterations per test
- Clear tagging with feature name and property number
- Descriptive failure messages indicating which file/location failed
- Integration with CI/CD pipeline for automated validation
