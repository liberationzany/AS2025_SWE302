# 🚢 Advanced Shipping Fee Calculator - Testing Implementation

A comprehensive test suite for shipping fee calculation functions, demonstrating black-box testing, equivalence partitioning, and boundary value analysis in Go.

---

## 📋 Table of Contents
- [📦 Project Overview](#-project-overview)
- [⚙️ Function Specifications](#%EF%B8%8F-function-specifications)
- [🧪 Testing Strategy](#-testing-strategy)
- [📊 Test Results](#-test-results)
- [🚀 Getting Started](#-getting-started)
- [🔧 Test Implementation](#-test-implementation)

---

## 📦 Project Overview

This project implements and tests two shipping fee calculation functions with comprehensive test coverage:

- **Advanced Function**: `CalculateShippingFee` – Multi-factor calculation with weight tiers, zones, and insurance
- **Basic Function**: `CalculateShippingFeeBasic` – Simplified weight-based calculation

**🔗 Repository**: [https://github.com/liberationzany/testin_practical3.git](https://github.com/liberationzany/testin_practical3.git)

---

## ⚙️ Function Specifications

### 1. `CalculateShippingFee(weight float64, zone string, insured bool) (float64, error)`

#### Business Rules

| Component | Rules | Details |
|-----------|-------|---------|
| **Weight** | Standard (0-10kg) | No surcharge |
| | Heavy (10-50kg) | +$7.50 surcharge |
| | Invalid | ≤0kg or >50kg |
| **Zone** | Domestic | $5.00 base fee |
| | International | $20.00 base fee |
| | Express | $30.00 base fee |
| | Invalid | Any other zone |
| **Insurance** | Enabled | +1.5% of (Base + Surcharge) |
| | Disabled | No additional cost |

**Formula**: `Fee = (Base + Surcharge) × (1 + 0.015 if insured)`

### 2. `CalculateShippingFeeBasic(weight float64, zone string) (float64, error)`

#### Business Rules

| Zone | Formula |
|------|---------|
| Domestic | $5.00 + (weight × $1.00) |
| International | $20.00 + (weight × $2.50) |
| Express | $30.00 + (weight × $5.00) |

**Weight Range**: 0 < weight ≤ 50 kg

---

## 🧪 Testing Strategy

### Test Design Methods

| Method | Application | Examples |
|--------|-------------|----------|
| **Equivalence Partitioning** | Group similar inputs | Weight: ≤0, 0-10kg, 10-50kg, >50kg |
| **Boundary Value Analysis** | Test edge cases | 0kg, 0.1kg, 10kg, 10.1kg, 50kg, 50.1kg |
| **Table-Driven Testing** | Go idiomatic pattern | 46 test cases in structured tables |

### Key Test Cases

| Category | Test Cases | Purpose |
|----------|------------|---------|
| Invalid Weight | 7 tests | Validate error handling |
| Invalid Zone | 7 tests | Zone validation |
| Boundary Values | 10 tests | Edge case verification |
| Valid Combinations | 22 tests | Business logic validation |

### Critical Boundaries Tested
- **0kg threshold**: Invalid vs. valid weights
- **10kg threshold**: Standard vs. heavy packages
- **50kg threshold**: Maximum valid weight
- **Zone validation**: Exact string matching
- **Insurance calculation**: 1.5% precision handling

---

## 📊 Test Results

### Coverage Summary
```
✅ 46/46 tests passing
✅ 100% statement coverage
✅ All business rules validated
✅ Complete error path testing
```

### Test Execution
```bash
# Run all tests
go test

# With detailed output
go test -v

# With coverage report
go test -cover

# Generate coverage profile
go test -coverprofile=coverage.out
go tool cover -html=coverage.out
```

### Example Test Scenarios

| Scenario | Weight | Zone | Insured | Expected Fee |
|----------|--------|------|---------|--------------|
| Minimum valid | 0.1kg | Domestic | No | $5.00 |
| Standard package | 5kg | International | Yes | $20.30 |
| Boundary (10kg) | 10kg | Express | Yes | $30.45 |
| Heavy package | 25kg | Domestic | No | $12.50 |
| Maximum valid | 50kg | Express | Yes | $38.06 |

---

## 🚀 Getting Started

### Prerequisites
- Go 1.21 or higher
- Git

### Installation
```bash
# Clone repository
git clone https://github.com/liberationzany/testin_practical3.git
cd testin_practical3

# Run tests
go test -v
```

### Project Structure
```
testin_practical3/
├── shipping.go           # Implementation
├── shipping_test.go      # 46 comprehensive test cases
├── go.mod               # Dependencies
└── README.md           # Documentation
```

---

## 🔧 Test Implementation

### Testing Features
- **Table-Driven Tests**: Organized test cases with descriptive names
- **Floating-Point Tolerance**: ±0.001 for financial calculations
- **Error Message Validation**: Substring matching for error content
- **Boundary Testing**: All critical thresholds verified
- **Combination Coverage**: All valid input combinations tested

### Key Test Functions
```go
// Example test structure
func TestCalculateShippingFee(t *testing.T) {
    tests := []struct {
        name     string
        weight   float64
        zone     string
        insured  bool
        want     float64
        wantErr  bool
        errMsg   string
    }{
        {
            name:    "standard domestic uninsured",
            weight:  5.0,
            zone:    "Domestic",
            insured: false,
            want:    5.00,
            wantErr: false,
        },
        // ... 45 more test cases
    }
}
```

### Challenges Addressed
1. **10kg Boundary**: Ensuring no surcharge at exactly 10kg
2. **Insurance Precision**: Handling 1.5% calculation with floating-point
3. **Error Consistency**: Validating error messages across invalid inputs
4. **Complete Coverage**: Achieving 100% statement coverage for both functions

---

## 🎓 Academic Context

### Course Information
- **Module**: SWE5006 - Software Testing & Quality Assurance
- **Assignment**: Practical 3 - Test Analysis & Implementation
- **Student ID**: 02230297
- **Academic Year**: 2025

### Learning Outcomes
- ✅ **Equivalence Partitioning**: Systematic input domain division
- ✅ **Boundary Value Analysis**: Critical edge case identification
- ✅ **Black-Box Testing**: Testing without implementation knowledge
- ✅ **Table-Driven Testing**: Go's idiomatic test organization
- ✅ **Complete Coverage**: 100% statement coverage achievement
- ✅ **Error Path Testing**: Comprehensive invalid input validation

### Testing Principles Demonstrated
| Principle | Application |
|-----------|-------------|
| **Black-Box Testing** | Tests based solely on specifications |
| **Equivalence Partitioning** | 8 distinct input partitions |
| **Boundary Value Analysis** | 6 critical boundaries tested |
| **Error Guessing** | Invalid zone variants tested |
| **Combinatorial Testing** | All parameter combinations |
---
Test Execution Evidence
This section provides visual evidence of the test execution and results.

Test Execution Results (go test -v)
Test 1 - Initial Test Run:
![Test Run 1](src/Screenshot%202025-12-06%20170437.png)
![Test Run 2](src/Screenshot%202025-12-06%20170418.png)

test Coverage Report:
![Coverage Report](src/Screenshot%202025-12-06%20170341.png)
---


*Built with Go • 46 Test Cases • 100% Coverage • Comprehensive Boundary Testing*