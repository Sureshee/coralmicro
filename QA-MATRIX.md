# Requirements Traceability Matrix (QA Matrix)

> **Purpose**: Track bidirectional traceability between requirements, implementation, and test cases.
> 
> **Maintained by**: QA Auditor Agent (BMAD Framework)

## Matrix

| Req ID | Requirement | Priority | Status | Implementation | Test Cases | Test Status | Last Updated |
|---------|-------------|----------|--------|----------------|------------|-------------|-------------|
| REQ-001 | Camera initialization must complete within 500ms | HIGH | DRAFT | - | - | - | 2024-01-15 |
| REQ-002 | Support TensorFlow Lite model inference on Edge TPU | CRITICAL | DRAFT | - | - | - | 2024-01-15 |
| REQ-003 | USB mass storage mode for firmware updates | MEDIUM | DRAFT | - | - | - | 2024-01-15 |
| REQ-004 | Audio recording at 16kHz sample rate | HIGH | DRAFT | - | - | - | 2024-01-15 |
| REQ-005 | Power consumption < 2W during inference | MEDIUM | DRAFT | - | - | - | 2024-01-15 |

## Status Definitions

- **DRAFT**: Requirement being defined
- **APPROVED**: Requirement approved for implementation
- **IMPLEMENTED**: Code written and committed
- **TESTED**: Test cases executed and passed
- **VERIFIED**: Validated in integration/system testing
- **RELEASED**: Included in official release

## Priority Levels

- **CRITICAL**: Core functionality, must have
- **HIGH**: Important feature, high priority
- **MEDIUM**: Valuable feature, medium priority
- **LOW**: Nice to have, lower priority

## Test Status Values

- **NOT_STARTED**: Tests not yet written
- **IN_PROGRESS**: Tests being developed
- **PASSED**: All tests passing
- **FAILED**: One or more tests failing
- **BLOCKED**: Testing blocked by dependencies
- **N/A**: Not applicable

## Example Entries (for reference)

These example entries show the expected format when requirements are fully traced:

| Req ID | Requirement | Priority | Status | Implementation | Test Cases | Test Status | Last Updated |
|---------|-------------|----------|--------|----------------|------------|-------------|-------------|
| REQ-EX1 | Example: LED control API | HIGH | TESTED | libs/base/led.cc:45-78 | TC-001, TC-002, TC-003 | PASSED | 2024-01-18 |
| REQ-EX2 | Example: I2C communication protocol | CRITICAL | VERIFIED | libs/base/i2c.cc:120-245 | TC-010, TC-011 | PASSED | 2024-01-17 |

## Test Case Mapping

### TC-001: LED Initialization Test
- **Requirements**: REQ-EX1
- **Type**: Unit Test
- **Location**: libs/base/led_test.cc
- **Status**: PASSED

### TC-002: LED On/Off Control Test
- **Requirements**: REQ-EX1
- **Type**: Unit Test
- **Location**: libs/base/led_test.cc
- **Status**: PASSED

### TC-003: LED Brightness Control Test
- **Requirements**: REQ-EX1
- **Type**: Integration Test
- **Location**: libs/base/led_test.cc
- **Status**: PASSED

## Gap Analysis

### Requirements without Implementation
- REQ-001: Camera initialization must complete within 500ms
- REQ-002: Support TensorFlow Lite model inference on Edge TPU
- REQ-003: USB mass storage mode for firmware updates
- REQ-004: Audio recording at 16kHz sample rate
- REQ-005: Power consumption < 2W during inference

### Requirements without Test Cases
- REQ-001: Camera initialization must complete within 500ms
- REQ-002: Support TensorFlow Lite model inference on Edge TPU
- REQ-003: USB mass storage mode for firmware updates
- REQ-004: Audio recording at 16kHz sample rate
- REQ-005: Power consumption < 2W during inference

### Implementation without Requirements
_(Code that doesn't map to documented requirements - should be minimized)_

## Coverage Statistics

- **Total Requirements**: 5
- **With Implementation**: 0 (0%)
- **With Test Cases**: 0 (0%)
- **Fully Traced**: 0 (0%)
- **Test Pass Rate**: N/A

## Instructions for QA Auditor Agent

### Adding New Requirements

1. Assign unique ID: REQ-XXX (sequential)
2. Add row to matrix with:
   - Clear requirement description
   - Priority level
   - Status = DRAFT initially
   - Empty implementation/test fields
3. Update gap analysis
4. Update statistics

### Updating Implementation

1. When code is committed:
   - Update Implementation column with file:line reference
   - Change Status: DRAFT → IMPLEMENTED
   - Update Last Updated date

### Adding Test Cases

1. Create test case entry with:
   - Unique TC-XXX ID
   - Requirement mapping
   - Test type (Unit/Integration/System)
   - Location in code
2. Update Test Cases column in matrix
3. Set Test Status based on execution
4. Update Last Updated date

### Verifying Traceability

1. For each PR:
   - Check if new code maps to requirements
   - Flag orphaned code (no requirement)
   - Update implementation references
   - Generate missing test cases
   - Update status progression

### Status Progression Rules

- DRAFT → APPROVED: Requirement reviewed and approved
- APPROVED → IMPLEMENTED: Code committed
- IMPLEMENTED → TESTED: Test cases pass
- TESTED → VERIFIED: Integration testing complete
- VERIFIED → RELEASED: Included in release

## Notes

- Keep matrix up-to-date with every PR
- Use file:line format for implementation references
- Test case IDs must be unique (TC-001, TC-002, etc.)
- Update gap analysis after each matrix change
- Recalculate coverage statistics after updates
- Archive obsolete requirements (don't delete)

---

**Last Matrix Update**: Auto-updated by QA Auditor Agent
**Next Review**: On next PR
