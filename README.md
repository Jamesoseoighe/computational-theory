# Computational Theory: SHA-256 Implementation and Security Analysis

**Author:** James Oseoighe  
**Module:** Computational Theory  
**Academic Year:** Winter 2025/26

This project explores computational complexity and security through the implementation and analysis of the SHA-256 cryptographic hash function. It demonstrates both the mathematical foundations of secure hashing and common vulnerabilities in password security.

## Overview

This repository contains a single Jupyter notebook (`problems.ipynb`) that implements the SHA-256 hashing algorithm from scratch, following the FIPS 180-4 standard. The implementation is fully self-contained and reproducible, requiring only standard Python libraries and numpy.

**Target Audience:** This project is designed for informed computing professionals, such as prospective employers or technical reviewers, who have a strong background in computing but may not be familiar with cryptographic implementations.

The project demonstrates understanding of:

- Cryptographic hash functions and their components
- The SHA-256 algorithm specification (FIPS 180-4)
- Computational complexity in security contexts
- Common password security vulnerabilities
- Clean code practices following PEP 8 guidelines

## What's Inside

The `problems.ipynb` notebook covers five main topics:

### Problem 1: Core SHA-256 Functions
Implementation of fundamental SHA-256 operations:
- **Helper functions**: Bitwise rotation (ROTR) and logical shifts (SHR)
- **Boolean functions**: Parity, Ch (Choose), and Maj (Majority)
- **Sigma functions**: Σ₀, Σ₁, σ₀, and σ₁ for message mixing

These functions form the building blocks of the SHA-256 compression function.

### Problem 2: Fractional Parts of Cube Roots
Generates the 64 round constants used in SHA-256 by computing the first 32 bits of the fractional parts of cube roots of the first 64 prime numbers. This demonstrates:
- How cryptographic constants are derived using mathematical principles
- Prime number generation
- Fixed-point arithmetic for extracting fractional components

### Problem 3: Padding and Message Parsing
Implements the SHA-256 message padding scheme according to FIPS 180-4:
- Adds padding bit (0x80)
- Extends message to proper length
- Appends 64-bit message length
- Parses padded message into 512-bit blocks

Includes comprehensive tests for various message lengths, including edge cases.

### Problem 4: SHA-256 Compression Function
The complete SHA-256 compression function (`hash()`) that:
- Takes an input state (8 × 32-bit words) and a 512-bit message block
- Expands the message block into a 64-word message schedule
- Applies 64 rounds of cryptographic mixing
- Returns the updated hash state

This is the core of the SHA-256 algorithm.

### Problem 5: Password Cracking via Dictionary Attack
Demonstrates the vulnerability of unsalted password hashes through a practical dictionary attack:
- Tests common passwords against SHA-256 hashes
- Shows why simple hashing is insufficient for password storage
- Explains security vulnerabilities (no salt, no iteration, deterministic)
- Provides recommendations for secure password hashing (PBKDF2, bcrypt, Argon2)

## Prerequisites

- Python 3.x
- Jupyter Notebook or JupyterLab
- Required libraries:
  - `numpy` - for uint32 operations
  - `math` - for mathematical operations
  - `typing` - for type hints
  - `hashlib` - for password cracking comparison

## Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/Jamesoseoighe/computational-theory.git
   cd computational-theory
   ```

2. Install required dependencies:
   ```bash
   pip install numpy jupyter
   ```

## Usage

The notebook is designed to be run sequentially from top to bottom. Each problem is clearly marked with a level 2 heading.

1. Launch Jupyter Notebook:
   ```bash
   jupyter notebook
   ```

2. Open `problems.ipynb` in the Jupyter interface

3. Run cells sequentially (Cell → Run All, or run each cell individually with Shift+Enter)

The notebook will display:
- Function implementations with detailed comments
- Example outputs demonstrating correctness
- Test cases with comprehensive validation
- Explanations of cryptographic concepts and security implications

**Note:** All code is self-contained within the notebook. No external data files are required.

## Educational Context

This project was created to understand:
- **Computational Theory**: How complex computational problems relate to security
- **Cryptographic Standards**: Implementation details of industry-standard algorithms
- **Security Vulnerabilities**: Real-world weaknesses in password storage systems
- **Applied Mathematics**: Using number theory and discrete mathematics in computing

## Key Takeaways

1. **SHA-256 is deterministic**: The same input always produces the same output, which is essential for verification but problematic for password storage without additional measures.

2. **Speed is a double-edged sword**: SHA-256's computational efficiency makes it excellent for data integrity but dangerous for password hashing, where slower is better.

3. **Security requires layers**: Modern password security needs salt, iteration, and proper key derivation functions (KDFs) like PBKDF2, bcrypt, or Argon2.

4. **Implementation matters**: Understanding how algorithms work helps identify when and how to use them correctly.

## References

- [FIPS 180-4: Secure Hash Standard (SHS)](https://nvlpubs.nist.gov/nistpubs/FIPS/NIST.FIPS.180-4.pdf) - Official SHA-256 specification
- [NIST Cryptographic Standards](https://csrc.nist.gov/projects/cryptographic-standards-and-guidelines)
- Password Security Best Practices:
  - [OWASP Password Storage Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Password_Storage_Cheat_Sheet.html)
  - [RFC 8018: PKCS #5 - PBKDF2](https://tools.ietf.org/html/rfc8018)

## Repository Structure

```
computational-theory/
├── README.md           # This file - project documentation
├── problems.ipynb      # Main notebook with all problem solutions
├── .gitignore         # Git ignore patterns for Python projects
└── .vscode/           # VS Code configuration (optional)
```

## Development Notes

This repository was developed incrementally over the assessment period, as evidenced by the commit history. The code follows Python best practices:
- **PEP 8** style guidelines for formatting and naming conventions
- **Meaningful variable names** for clarity
- **Modular code structure** with clear separation of concerns
- **Comprehensive comments** explaining implementation details
- **Test cases** validating correctness against known standards

## Assessment Context

This repository was created as part of the Computational Theory module assessment (Winter 2025/26). It demonstrates:
- Research into cryptographic standards (FIPS 180-4)
- Implementation of complex algorithms from specification
- Understanding of computational security concepts
- Professional code documentation and presentation practices

## License

This project is for educational purposes as part of an academic assessment.
