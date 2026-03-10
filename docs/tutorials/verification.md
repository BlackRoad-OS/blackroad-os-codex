# ✅ Mathematical Verification Tutorial

Learn how to use the Codex to verify mathematical code automatically.

---

## What Is Verification?

The Codex can automatically check:
- **Mathematical expressions** — `E = mc²`, matrix ops, integrals
- **Type consistency** — are the types used consistently?
- **Loop invariants** — do your loops do what you think?
- **Symbolic equivalence** — are two expressions mathematically the same?

---

## Verify a Component

```bash
./blackroad-codex-verification-suite.sh verify <component_id> <file_path>
```

**Example output:**
```
✅ Type checking passed
✅ Found 4 calculations
✅ Symbolic computation verified
   E = mc² → LaTeX: E = mc^{2}
   a*(b+c) simplified to a*b + a*c (distributive property)
```

---

## List Built-in Math Identities

The Codex ships with 76 mathematical identities:

```bash
./blackroad-codex-verification-suite.sh identities
```

Includes: Pythagorean theorem, Euler's formula, distributive/associative/commutative laws, and more.

---

## Python API

```python
from blackroad_codex_symbolic import SymbolicComputationEngine

engine = SymbolicComputationEngine()

# Check symbolic equivalence
print(engine.verify_symbolic_equivalence("a*(b+c)", "a*b+a*c"))  # True

# Simplify
print(engine.simplify("x + 0"))  # x

# Generate LaTeX
print(engine.to_latex("E = m * c**2"))  # E = mc^{2}
```

---

## Verification Dashboard

```bash
./blackroad-codex-verification-suite.sh dashboard
```

Shows all components that have been verified, with pass/fail status.

---

*See [CODEX_VERIFICATION_GUIDE.md](../CODEX_VERIFICATION_GUIDE.md) for the full guide.*
