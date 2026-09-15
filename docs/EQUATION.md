# Skokv1 Encryption

## Master Container Stream
**Y** = H || S || L || (i=0 -> N-1) [ Y[i] ]

## Encryption Equation
**Y[i]** = RotL( ( (~RotL(((D[i] ^ K[i]) * ((K[i] ^ i) | 1)) % 256, 3) % 256) ^ K[i] ^ C[i] ), (K[i] ^ i) % 8 )

## Dependency Variables
**K[i]** = ( Bits_64(Lorenz_X(sd, i)) >> 16 ) % 256

**C[i]** = ( i == 0 ? (sd >> 24) % 256 : Y[i-1] )

**sd** = ( (salt ^ DJB2(boot_id)) * (Z^M) + Sum[ key[k] * Z^(M-1-k) ] ) % (2^64)