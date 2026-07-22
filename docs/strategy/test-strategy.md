# Money Transfer Feature Test Strategy

| Field | Value |
| --- | --- |
| Feature | Money transfer |
| Owner | Phani Pramod Kruttiventi |
| Version | 2.1 |
| Last updated | 2026-07-22 |

## Objective

Verify that a customer can complete a money transfer with the correct amount, FX rate, fee, UPI recipient, confirmation details, and final status.

## Feature flow

`Enter amount → Receive FX quote → Add/select UPI recipient → Review fees and rate → Confirm transfer → Track status`

## Scope

### In scope

- Amount validation
- FX rate, fee, rounding, and quote expiry
- UPI recipient validation and selection
- Review-page details
- Transfer confirmation and duplicate prevention
- Failure, retry, and status handling
- Basic read-only checks on Beacon's public transfer page

### Out of scope

- Account opening, funding, cards, and bill payments
- India-to-Canada remittance and other transfer corridors
- General application regression
- Real money transfers
- Production API, database, security, performance, and mobile testing

## Test approach

| Test area | Coverage |
| --- | --- |
| Functional | Complete the transfer flow and verify expected results |
| Negative | Invalid amount, invalid recipient, expired quote, failure, and retry |
| Boundary | Minimum, maximum, zero, negative, decimal, and over-limit amounts |
| Usability | Clear amounts, fees, recipient details, messages, and actions |
| Compatibility | Main customer flow on supported browsers and devices |
| Regression | Re-run critical transfer scenarios after changes |

## Test environment and data

- Beacon public website for safe, read-only checks
- An authorized QA environment is required to execute the complete transfer flow
- Synthetic customer, recipient, quote, and transfer data must be used

No Beacon account will be created and no real transfer or customer data will be used.

## Main risks

Testing will prioritize incorrect calculations, expired quotes, wrong recipients, duplicate transfers, unauthorized transfers, provider failures, and incorrect status.

## Entry criteria

- Scope and expected flow are agreed
- Test environment is available
- Synthetic test data is ready
- The build can be identified

## Exit criteria

- All critical and high-risk checks have run
- No open issue can cause a duplicate, unauthorized, incorrect, or misdirected transfer
- Critical regression checks pass
- Failed and blocked checks are explained
- Test results and open risks are reported

## Defect handling

Defects will include a clear title, build, steps, expected result, actual result, severity, evidence, and related risk ID.

- **Critical:** Financial loss, duplicate or unauthorized transfer, wrong recipient, or sensitive-data exposure
- **High:** Main flow blocked or incorrect amount, rate, fee, or final status
- **Medium:** Partial impact with a workaround
- **Low:** Minor content or layout issue

Critical defects and High defects affecting transfer correctness block release.

## Reporting

The final report will show:

- Passed, failed, blocked, and not-run checks
- Open defects by severity
- Critical and high-risk coverage
- Release blockers
- Go, Go with known risks, or No-Go recommendation

## Release decision

The quality lead gives a recommendation after reviewing test results, open defects, and failed or blocked checks.

| Decision | Criteria |
| --- | --- |
| Go | Exit criteria are met and no release blocker is open |
| Go with known risks | No Critical defect is open, and the release owner accepts the documented remaining issues |
| No-Go | A release blocker is open, critical checks failed, or test evidence is incomplete |

The release owner makes the final decision. Any accepted issue must have an owner, impact, workaround, and follow-up action.

## Test summary and release recommendation

Complete this section at the end of testing.

| Item | Result |
| --- | --- |
| Build/version tested | |
| Test period | |
| Passed | |
| Failed | |
| Blocked | |
| Critical defects open | |
| High defects open | |
| Release blockers | |
| Recommendation | Go / Go with known risks / No-Go |

**Summary:**

**Open risks:**

**Release-owner decision:**

## Limitation

Beacon is assessed only through public, read-only behavior. The complete transfer flow cannot be executed without an authorized QA environment, test account, and synthetic financial data. This document therefore presents the test approach and does not claim completed end-to-end test evidence.
