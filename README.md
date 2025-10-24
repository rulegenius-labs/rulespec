# RuleSpec — The Open Specification for Data Validation & Data Contracts
🔹 **Official repository of [RuleGenius](https://www.rulegenius.com)**

[![License](https://img.shields.io/badge/license-Apache%202.0-green)](LICENSE)
[![Type](https://img.shields.io/badge/repo-documentation-blue)]()
[![Domain](https://img.shields.io/badge/domain-rulegenius.com-blue)](https://www.rulegenius.com)
[![Domain](https://img.shields.io/badge/domain-rulespec.org-blue)](https://www.rulespec.org)
![Topic](https://img.shields.io/badge/topic-DSL-lightgrey)
![Topic](https://img.shields.io/badge/topic-Data%20Contracts-lightgrey)
![Topic](https://img.shields.io/badge/topic-Data%20Validation-lightgrey)

> **RuleSpec** is an open, human-readable DSL for defining  
> data validation, transformation, and data contracts across systems.  
> This repository contains the official grammar, documentation, examples, and reference tests.

**RuleSpec** defines a human-readable, interoperable standard for describing data validation logic and data contracts.

It is maintained by [RuleGenius Labs](https://github.com/rulegenius-labs)  
and powers the commercial [RuleGenius Platform](https://www.rulegenius.com).

---

## 🧠 Purpose

RuleSpec allows organizations to describe:

- Field-level **validations**
- Cross-field **consistency rules**
- Data **contract metadata** (frequency, retention, fail policy)
- Optional **transformations** (for preprocessing or normalization)

All in plain text, with syntax designed for both humans and machines.

---

## 📘 Example

```
@contract supplier_product_feed_v1
@version 1.0
@description "Supplier product data contract"
@format csv delimiter="," encoding="utf-8" max_rows=50000

@field product_id type=string required unique
@field price type=number required min=0
@field updated_at type=date required format="YYYY-MM-DD"

validate "product_id" is not_empty
validate "price" is in_range 0..100000
```

---

## ⚙️ Components

- **Grammar:** [grammar/rulespec.ebnf](grammar/rulespec.ebnf)  
- **ANTLR Grammar:** [grammar/rulespec.g4](grammar/rulespec.g4)  
- **Docs:** [docs/specification.md](docs/specification.md)  
- **Reference Parser:** [reference/parser_demo.py](reference/parser_demo.py)

---

## 🪶 License

Released under the [Apache 2.0 License](LICENSE).

> “RuleSpec” and “RuleGenius” are trademarks of RuleGenius.  
> Implementations may reference the RuleSpec format but may not use these names for commercial branding without written permission.

---

## 💼 Commercial Implementations

[RuleGenius](https://www.rulegenius.com) provides:

- High-performance validation and data governance engine  
- CLI and API for integrating RuleSpec in production pipelines  
- Managed dashboards and audit logs  

Learn more at [rulegenius.com](https://www.rulegenius.com).
