# Bitwise Operators

## The Operators

| Operator     | Symbol | Description |  Mathematical Equivalent |
|-------------|--------|-------------|----------|
| AND         | `&`    | Copies a bit to the result if it exists in both operands. Performs bitwise AND: result is 1 only when both bits are 1. | Masking bits |
| OR          | `\|`    | Copies a bit if it exists in either operand. Performs bitwise OR: result is 0 only when both bits are 0. | Combine bit flags |
| NOT         | `~`    | Binary One’s Complement. Flips all bits (0 → 1, 1 → 0). | ~n = -(n + 1) |
| Left Shift  | `<<`   | Shifts bits left by the number specified in the right operand. Equivalent to multiplying by 2^(right operand). | Toggle bits |
| Right Shift | `>>`   | Shifts bits right by the number specified in the right operand. | n << k = n × 2^k |
| XOR         | `^`    | Copies the bit if it is set in one operand but not both (exclusive OR). | Integer Division: n >> k = floor(n / 2^k) |

## Examples

| Operator     | Example (Binary) | Result (Decimal) |
|-------------|------------------|------------------|
| AND         | 0101 & 0011 = 0001 | 5 & 3 = 1 |
| OR          | 0101 \| 0011 = 0111 | 5 \| 3 = 7 |
| NOT         | ~00000101 = 11111010 | ~5 = -6 (in 2's complement) |
| XOR         | 0101 ^ 0011 = 0110 | 5 ^ 3 = 6 |
| Left Shift  | 0101 << 1 = 1010 | 5 << 1 = 10 |
| Right Shift | 0101 >> 1 = 0010 | 5 >> 1 = 2 |

## 4-Bit (Nibble) Representation

Each hexadecimal digit represents 4 binary bits.

| Binary | Hex |
|--------|-----|
| 0000   | 0   |
| 0001   | 1   |
| 0010   | 2   |
| 0011   | 3   |
| 0100   | 4   |
| 0101   | 5   |
| 0110   | 6   |
| 0111   | 7   |
| 1000   | 8   |
| 1001   | 9   |
| 1010   | A   |
| 1011   | B   |
| 1100   | C   |
| 1101   | D   |
| 1110   | E   |
| 1111   | F   |

### Conversion Example

Binary: `10101100`

Group into 4 bits:
`1010 1100`

Convert each group:

`1010 → A`

`1100 → C`

Result:
`0xAC`

### Why Hex is Useful

- 1 hex digit = 4 bits
- 2 hex digits = 1 byte (8 bits)
- Makes binary shorter and readable


