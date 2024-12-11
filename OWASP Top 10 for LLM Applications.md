# OWASP Top 10 for LLM Applications

## LLM01: Prompt Injection
- Leads To:
  - LLM07: System Prompt Leakage
  - LLM02: Sensitive Information Disclosure
  - LLM09: Misinformation
  - LLM10: Unbounded Consumption
- Facilitates Triggering/Exploiting:
  - LLM05: Improper Output Handling
  - LLM06: Excessive Agency
- Related to OWASP Web App Top 10:
  - A03:2021-Injection
- MITRE ATLAS:
  - AML.T0051.000 (LLM Prompt Injection: Direct)
  - AML.T0051.001 (LLM Prompt Injection: Indirect)
  - AML.T0054 (LLM Jailbreak Injection: Direct)

## LLM02: Sensitive Information Disclosure
- Closely Related:
  - LLM07: System Prompt Leakage
- OWASP Web App Equivalent:
  - A01:2021-Broken Access Control
- MITRE ATLAS:
  - AML.T0024.000 (Infer Training Data Membership)
  - AML.T0024.001 (Invert ML Model)
  - AML.T0024.002 (Extract ML Model)

## LLM03: Supply Chain
- Leads To:
  - LLM04: Data and Model Poisoning
  - LLM08: Vector and Embedding Weaknesses
- Indirectly Contributes To:
  - LLM09: Misinformation
- OWASP Web App Equivalent:
  - A06:2021-Vulnerable and Outdated Components
- MITRE ATLAS:
  - AML.T0010 (ML Supply Chain Compromise)

## LLM04: Data and Model Poisoning
- Once Poisoned Results In:
  - LLM09: Misinformation
  - LLM08: Vector and Embedding Weaknesses
- OWASP Web App Equivalent:
  - A08:2021-Software and Data Integrity Failures
- MITRE ATLAS:
  - AML.T0018 (Backdoor ML Model)

## LLM05: Improper Output Handling
- Can Be Exploited By:
  - LLM01: Prompt Injection (feedback loop)
- Intensifies:
  - LLM10: Unbounded Consumption
- OWASP Web App Equivalent:
  - A03:2021-Injection
- (No direct MITRE technique, but relates to injection scenarios)

## LLM06: Excessive Agency
- Excessive Privileges Increase:
  - LLM10: Unbounded Consumption (resource abuse)
- Intensifies Other Risks:
  - Data Poisoning, Embedding Weaknesses, etc.
- OWASP Web App Equivalent:
  - A01:2021-Broken Access Control
- (No direct specific MITRE technique; relates to access/abuse)

## LLM07: System Prompt Leakage
- Reveals Info Aiding:
  - LLM01: Prompt Injection
  - LLM02: Sensitive Information Disclosure
- Ultimately Affects:
  - LLM09: Misinformation
- OWASP Web App Equivalent:
  - A05:2021-Security Misconfiguration
- (Related to AML.T0051.* from MITRE due to prompt injection linkage)

## LLM08: Vector and Embedding Weaknesses
- Influenced By:
  - LLM04: Data and Model Poisoning
  - LLM03: Supply Chain
- Leads To:
  - LLM09: Misinformation
- OWASP Web App Equivalent:
  - A08:2021-Software and Data Integrity Failures
- MITRE ATLAS:
  - (Likely AML.T0024.* for model inversion/exfiltration)

## LLM09: Misinformation
- Originates From:
  - LLM01: Prompt Injection
  - LLM04: Data and Model Poisoning
  - LLM08: Vector and Embedding Weaknesses
- OWASP Web App Equivalent:
  - A04:2021-Insecure Design
- MITRE ATLAS:
  - AML.T0048.002 (Societal Harm)

## LLM10: Unbounded Consumption
- Exacerbated By:
  - LLM01: Prompt Injection
  - LLM06: Excessive Agency
- Worsened By:
  - LLM05: Improper Output Handling
- OWASP Web App Equivalent:
  - A04:2021-Insecure Design
- MITRE ATLAS:
  - AML.T0029 (Denial of ML Service)
  - AML.T0034 (Cost Harvesting)
