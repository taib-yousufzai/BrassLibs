# Implementation Plan: Brand Name Standardization

## Overview

This implementation plan addresses the standardization of company naming across three React projects: quotation system, library system, and mood board builder. The approach involves systematic file updates to replace "Brass Space" with "Brass Space Interior" or "Brass Space Interior Solution" in user-facing content, configuration files, code comments, and documentation. Each task is designed to be atomic and testable, with property-based tests ensuring comprehensive validation.

## Tasks

- [x] 1. Set up testing infrastructure for brand name validation
  - Install fast-check library for property-based testing in each project
  - Configure Jest to support property-based tests
  - Create test utilities for file scanning and content validation
  - _Requirements: 1.1, 5.1, 6.1_

- [ ]* 1.1 Write property test for user-facing content consistency
  - **Property 1: User-Facing Content Consistency**
  - **Validates: Requirements 1.1, 1.3, 1.4, 2.1, 2.2, 2.3, 2.4, 2.5, 3.2, 3.3, 4.1, 4.2**

- [ ]* 1.2 Write property test for package name consistency
  - **Property 2: Package Name Consistency**
  - **Validates: Requirements 5.1, 5.2, 5.3**

- [ ]* 1.3 Write property test for code comments and documentation consistency
  - **Property 3: Code Comments and Documentation Consistency**
  - **Validates: Requirements 6.1, 6.2, 6.3**


- [x] 2. Update Quotation System components and configuration
  - [x] 2.1 Update Header component to use "Brass Space Interior"
    - Modify quotation/quotation/quotation/src/components/Header.jsx
    - Replace "Brass Space" with "Brass Space Interior" in header display
    - _Requirements: 2.1_

  - [x] 2.2 Update QuotePreview component to use "Brass Space Interior"
    - Modify quotation/quotation/quotation/src/components/QuotePreview.jsx
    - Replace all instances of "Brass Space" in company info, bank details, signature, and footer
    - _Requirements: 2.2, 2.3, 2.4, 2.5_

  - [x] 2.3 Update ViewQuotation page to use "Brass Space Interior"
    - Modify quotation/quotation/quotation/src/pages/ViewQuotation.jsx
    - Replace all instances of "Brass Space" in company info, bank details, signature, and footer
    - _Requirements: 2.2, 2.3, 2.4, 2.5_

  - [x] 2.4 Update Firebase configuration comments
    - Modify quotation/quotation/quotation/src/firebase.js
    - Update comment to reference "Brass Space Interior"
    - _Requirements: 6.1_

  - [x] 2.5 Update package.json to use standardized naming
    - Modify quotation/quotation/quotation/package.json
    - Change package name from "brass-space-quotation-builder" to "brass-space-interior-quotation-builder"
    - _Requirements: 5.1, 5.3_

  - [ ]* 2.6 Write unit tests for Quotation System components
    - Test Header component renders "Brass Space Interior"
    - Test QuotePreview displays correct name in all sections
    - Test ViewQuotation displays correct name in all sections
    - _Requirements: 2.1, 2.2, 2.3, 2.4, 2.5_

- [x] 3. Checkpoint - Verify Quotation System changes
  - Ensure all tests pass, ask the user if questions arise.

- [x] 4. Update Library System components and configuration
  - [x] 4.1 Update LocalAuthContext for admin references
    - Modify library (2)/library/Photolibrary/src/context/LocalAuthContext.jsx
    - Update any admin email references to use "Brass Space Interior Admin"
    - _Requirements: 3.1_

  - [x] 4.2 Update Register page for company references
    - Modify library (2)/library/Photolibrary/src/pages/Register.jsx
    - Update any company references to use "Brass Space Interior"
    - _Requirements: 3.2_

  - [x] 4.3 Update roleManager utility for admin references
    - Modify library (2)/library/Photolibrary/src/utils/roleManager.js
    - Update any company references to use "Brass Space Interior" or "Brass Space Interior Admin"
    - _Requirements: 3.1, 3.3_

  - [x] 4.4 Update Library package.json if needed
    - Verify and update library (2)/library/Photolibrary/package.json
    - Ensure package name follows "brass-space-interior" pattern if applicable
    - _Requirements: 5.1_

  - [ ]* 4.5 Write unit tests for Library System components
    - Test admin references use "Brass Space Interior Admin"
    - Test registration flow displays correct company name
    - Test role manager displays correct company references
    - _Requirements: 3.1, 3.2, 3.3_

- [x] 5. Checkpoint - Verify Library System changes
  - Ensure all tests pass, ask the user if questions arise.


- [x] 6. Update Mood Board System components and configuration
  - [x] 6.1 Verify and update autoGeneratorStore
    - Review mood_board-builder/src/store/autoGeneratorStore.js
    - Verify "Brass Space Interior Solution" is used correctly
    - Update email/website context if needed to reference full brand name
    - _Requirements: 4.1, 4.2_

  - [x] 6.2 Update Mood Board package.json if needed
    - Verify and update mood_board-builder/package.json
    - Ensure package name follows "brass-space-interior" pattern if applicable
    - _Requirements: 5.1_

  - [ ]* 6.3 Write unit tests for Mood Board System components
    - Test company information displays "Brass Space Interior Solution"
    - Test email/website references maintain brand consistency
    - _Requirements: 4.1, 4.2_

- [x] 7. Update documentation and comments across all projects
  - [x] 7.1 Scan and update all code comments
    - Search for "Brass Space" in comments across all three projects
    - Replace with "Brass Space Interior" in all code comments
    - _Requirements: 6.1_

  - [x] 7.2 Update documentation files
    - Search for "Brass Space" in all .md files across projects
    - Replace with "Brass Space Interior" or "Brass Space Interior Solution" as appropriate
    - _Requirements: 6.2_

- [x] 8. Final validation and integration
  - [x] 8.1 Run all property-based tests across projects
    - Execute property tests for user-facing content consistency
    - Execute property tests for package name consistency
    - Execute property tests for comments and documentation consistency
    - Verify all tests pass with 100+ iterations
    - _Requirements: 1.1, 5.1, 6.1, 6.2_

  - [x] 8.2 Perform manual verification
    - Run quotation system and verify company name displays correctly
    - Generate sample quotation and verify all sections
    - Test library registration flow
    - Create mood board and verify company references
    - _Requirements: 1.1, 2.1, 2.2, 3.2, 4.1_

  - [ ]* 8.3 Write integration tests for cross-project consistency
    - Test that all three projects use consistent naming
    - Test that no abbreviated forms exist in any project
    - _Requirements: 1.1, 1.3_

- [x] 9. Final checkpoint - Complete validation
  - Ensure all tests pass, ask the user if questions arise.

## Notes

- Tasks marked with `*` are optional and can be skipped for faster implementation
- Each task references specific requirements for traceability
- Checkpoints ensure incremental validation after each major system update
- Property tests validate universal correctness across all files
- Unit tests validate specific components and edge cases
- Manual verification ensures visual correctness in running applications
