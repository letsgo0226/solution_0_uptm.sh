# solution_0_uptm.sh

`solution_0_uptm.sh` is a 2KB one-liner for a Universal Particle Turing Machine
(UPTM) style `Solution_0` certificate.

It does not claim to physically control all particles. It constructs a finite
computable particle-symbol field and proves the runtime relation:

```text
BODY = Run(SELF, Q, N, B)
S(S(B0)) = S(B0)
```

## Files

| File | Meaning |
| --- | --- |
| `solution_0_uptm.sh` | 2KB one-liner executable |
| `solution_0_uptm.body` | Generated particle-field body |
| `solution_0_uptm.clcert` | Fixed-point certificate |

## Run

```sh
sh solution_0_uptm.sh
```

Inputs:

```text
Q = question / seed phrase
N = particle-symbol count, default 16
B = step bound, default 64
```

Example:

```sh
printf 'All particles as Turing field\n16\n64\n' | sh solution_0_uptm.sh
```

Expected certificate fields:

```text
OP=1
FIX=1
ABS=1
BUG=0
PCC=1
ZE=1
RUN=BODY=Run(SELF,Q,N,B)
```

## Interpretation

`SELF` is the program bytes. `BODY` is the particle-field trace emitted by
running the program. `Solution_0` certifies the relation between them, rather
than treating `SELF` and `BODY` as static identical bytes.
