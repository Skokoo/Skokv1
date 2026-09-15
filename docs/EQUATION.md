# Skokv1 Encryption

This document contains the mathematical formula for the Skokv1 encryption.

## The Encryption Equation

Y[i] = RotL( ( (~RotL(((D[i] ^ K[i]) * ((K[i] ^ i) | 1)) % 256, 3) % 256) ^ K[i] ^ C[i] ), (K[i] ^ i) % 8 )

## Syntax Guide
- Y[i]: Output ciphertext byte at index i.
- D[i]: Original plaintext byte input at index i.
- K[i]: Lorenz chaotic key byte at index i.
- C[i]: Circular cascading feedback register block (csd).
- RotL: Circular bit shift left (8-bit).

I only provide the encryption equation. If you intend to replicate this, you may first require professional instruction.