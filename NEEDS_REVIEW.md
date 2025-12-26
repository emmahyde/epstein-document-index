# Entities Requiring Human Review

This file tracks entities with ambiguous name matches that may contain false positives. When the entity extraction uses broad variations (e.g., matching "Kevin" for "Kevin Spacey"), documents may be incorrectly attributed.

---

## Review Status

| Entity | Issue | Status | Notes |
|--------|-------|--------|-------|
| Harvey Weinstein | Was matching all "Weinstein" | **FIXED** | Reduced from 111 to 19 docs; Marc A. Weinstein split out |
| Marc A. Weinstein | New entity | **ADDED** | 70 docs - attorney for Epstein Estate |
| Kevin Spacey | Was matching all "Kevin" | **FIXED** | Reduced from 31 to 2 docs |

---

## Flagged for Future Review

The following entities use broad name variations that may cause false positives:

### High Risk (common first/last names)

| Entity | Problematic Variations | Recommended Action |
|--------|----------------------|-------------------|
| Woody Allen | `["Allen", "Woody"]` | Review - "Allen" is very common |
| Bill Clinton | `["Clinton", "Bill"]` | Review - "Bill" matches other Bills |
| Bill Gates | `["Gates", "Bill"]` | Review - "Bill" matches other Bills |
| Donald Trump | `["Trump", "Donald"]` | Review - verify all matches |
| Prince Andrew | `["Andrew", "Prince"]` | Review - "Andrew" is common |

### Medium Risk

| Entity | Problematic Variations | Recommended Action |
|--------|----------------------|-------------------|
| David Boies | `["Boies", "David"]` | Review - "David" is common |
| Leon Black | `["Black", "Leon"]` | Review - "Black" may match descriptions |
| Roy Black | `["Black", "Roy"]` | Review - "Black" may match descriptions |
| Steve Bannon | `["Bannon", "Steve"]` | Review - "Steve" is common |

---

## Methodology for Review

When reviewing ambiguous matches:

1. **Exact match search**: Search for full name (e.g., "Kevin Spacey")
2. **Context verification**: Read surrounding text to confirm identity
3. **Split if needed**: Create separate entries for different people with same surname
4. **Document confidence**: Note which docs are confirmed vs. uncertain

---

## Corrections Log

| Date | Entity | Change | Docs Affected |
|------|--------|--------|---------------|
| 2024-12-26 | Harvey Weinstein | Reduced to exact matches only | -92 docs |
| 2024-12-26 | Marc A. Weinstein | Created new entity (Epstein estate lawyer) | +70 docs |
| 2024-12-26 | Kevin Spacey | Reduced to exact matches only | -29 docs |

---

## How to Report Issues

If you find incorrectly attributed documents:

1. Note the EFTA document number
2. Note the entity it's incorrectly assigned to
3. Provide context showing the actual person referenced
4. Submit via GitHub issue or PR
