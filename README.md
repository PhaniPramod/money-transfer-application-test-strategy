# Money Transfer Application Test Strategy

A feature-level test strategy for a money-transfer flow.

## System under test

This project uses the money-transfer feature described on [Beacon](https://www.mybeacon.ca/) as its real-world reference. Scope is limited to the following customer journey:

`Enter amount → Receive FX quote → Add or select UPI recipient → Review fees and rate → Confirm transfer → Track status`

Other Beacon products and application features are outside the project scope.

This repository is an independent black-box assessment. It is not affiliated with, endorsed by, or commissioned by MyBeacon Services Inc. It contains no proprietary information and does not claim access to Beacon source code, internal APIs, databases, test environments, or customer data.

## Ethical testing boundary

Testing against Beacon is limited to safe, read-only behavior on publicly accessible web pages. This project will not:

- Execute real financial transactions
- Create customer accounts
- Discover or call undocumented private endpoints
- Perform vulnerability scanning, penetration testing, or load testing
- Collect personal, financial, authentication, or production data

## Repository structure

```text
.
├── docs/
│   └── strategy/test-strategy.md
├── LICENSE
└── README.md
```

## Evidence status

| Area | Current status |
| --- | --- |
| Feature selection | Money transfer confirmed |
| Testing boundary | Confirmed |
| Test strategy | [Baseline complete](docs/strategy/test-strategy.md) |
| Test summary and release decision | Included in the test strategy |

## License

The original material in this repository is available under the MIT License. Beacon names, marks, product content, and services remain the property of their respective owners.
