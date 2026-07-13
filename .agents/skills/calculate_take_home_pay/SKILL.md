---
name: calculate-take-home-pay
version: 0.0.1
description: Use this skill for all Australian take-home pay / net salary calculations. Includes tax brackets, Medicare Levy, Superannuation (Super Guarantee), HELP/HECS debt, and common Australian payroll deductions.
---

# Calculate Take-Home Pay (Australia)

## Purpose
Calculate accurate **net (take-home) pay** for Australian residents, including income tax, Medicare Levy, Superannuation, and other common deductions.

## Official References

See `./url-references.md` for the complete list of official ATO links and recommended resources.

## When to trigger this skill
- User asks for "take home pay", "net salary", "after tax pay", "paycheck calculator", "salary after tax" in an Australian context.
- Mentions gross salary, super, HELP debt, salary sacrifice, etc.

## Core Instructions

1. **Always confirm key details**
   - Gross annual salary (or monthly/fortnightly)
   - Superannuation rate (default: 11.5% for 2025-26)
   - Tax-free threshold eligibility
   - HELP/HECS debt (yes/no + approximate balance if known)
   - Any salary sacrifice or pre-tax deductions
   - Residency status (assume Australian tax resident unless stated otherwise)

2. **Required Outputs**
   Provide a clear breakdown:
   - **Gross Annual Salary**
   - Superannuation (employee + employer contributions)
   - Taxable Income (after salary sacrifice if any)
   - Income Tax
   - Medicare Levy
   - HELP Repayment (if applicable)
   - **Net Annual Pay**
   - **Net Fortnightly / Monthly Pay** (most useful for clients)
   - Effective tax rate

3. **Use current Australian tax rules**
   - Apply the latest resident tax brackets and Medicare Levy.
   - Include Low and Middle Income Tax Offset (LMITO) / Low Income Tax Offset (LITO) where applicable.
   - Super Guarantee is paid **on top** of gross salary (not deducted from employee pay).

4. **Best Practices**
   - Always show both **annual** and **fortnightly** figures.
   - Clearly state the financial year being used (e.g., 2025–26).
   - Mention that this is an estimate only and recommend professional tax advice.
   - Offer to model different scenarios (salary sacrifice, extra super contributions, etc.).

## Common Australian Scenarios to Handle
- Standard PAYG employee
- Salary packaging / salary sacrifice
- Contractors vs employees
- High income earners (Medicare Levy Surcharge)
- Low income earners (tax offsets)

## Example Response Structure

**Gross Annual Salary**: $120,000  
**Superannuation (11.5%)**: $13,800 (paid by employer)  
**Taxable Income**: $120,000  

**Deductions**:
- Income Tax: $XX,XXX
- Medicare Levy: $X,XXX
- HELP Repayment: $X,XXX (if applicable)

**Net Annual Pay**: $XX,XXX  
**Net Fortnightly Pay**: $X,XXX  

Would you like me to adjust for salary sacrifice or different super contributions?

---