# PureNums

Quantum random number generation with cryptographic purification.

---

## Purpose & Impact

True randomness matters. Pseudo-random generators follow patterns - predictable if you know the seed. For applications requiring genuine unpredictability, PureNums fetches entropy from quantum vacuum fluctuations and purifies it through cryptographic hashing to produce statistically uniform output.

**Value**: When randomness must be unassailable, this delivers.

---

## Philosophy

**From mind to matter.**

The question was simple: how do you get truly random numbers? Not pseudo-random. Not "good enough." Genuinely unpredictable.

The answer required understanding quantum mechanics, cryptographic hashing, and statistical validation. This project demonstrates the ability to identify a real problem, research the necessary domains, and synthesize them into a working solution.

---

## Technical Highlights

### SHA-256 Entropy Purification

Raw quantum data can have biases from measurement equipment. Cryptographic hashing redistributes entropy uniformly:

```python
def _purify_chunk(self, hex_chunk):
    raw_bytes = bytes.fromhex(hex_chunk)
    hasher = hashlib.sha256(raw_bytes)
    purified_hex = hasher.hexdigest()
    return bin(int(purified_hex, 16))[2:].zfill(256)
```

One 128-character hex chunk → 256 purified bits with maximum entropy density.

### Rejection Sampling for Unbiased Output

When generating numbers 1-70 (Powerball), naive modulo creates bias. Rejection sampling ensures perfect uniformity:

```python
if num < max_val:
    value = num + 1
    if value not in current_set:
        current_set.add(value)
```

Numbers outside the valid range are discarded, not wrapped - guaranteeing each value has equal probability.

---

## Challenges Overcome

**Problem**: API rate limits vs entropy requirements. Large requests need thousands of random bits, but the ANU API has length limits.

**Solution**: Pre-calculate exact entropy needs based on rejection sampling probability, fetch in single optimized requests, and gracefully handle partial fulfillment.

---

## Technologies

Python | ANU Quantum API | SHA-256 | Statistical validation

---

## Media

- [ ] **Terminal screenshot**: Validation benchmark showing all statistical tests passing
- [ ] **Terminal screenshot**: Generation output showing multiple unique sets created
