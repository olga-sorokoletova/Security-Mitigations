# Security Committments and Mitigations by providers of general-purpose AI models with Systemic Risk
Based General-Purpose AI Code of Practice.

## What kind of security-related systemic risks we consider:
- Possession of the unreleased weights,
- Possession of *associated assets* of the model. Example of the "associated asset": unreleased algorithmic insights.

## Threat actor we want to defend against:
- Highly motivated, well-resourced, non-state. Includes: insider threats (i.e. employees of the provider).

## Mitigation requirements:
- Comitted to follow **RAND SL3 benchmark**, 
(ref. general description of the Commitment 12)
- Encouraged to follow **RAND SL4 benchmark** and above, if there is a reason to expect state-level threat actor attacks, 
(ref. general description of the Commitment 12)
	+ SL stands for Security Level,
	+ The higher Security Level is, the stricter mitigations are and the more skilled and resourced the threat actor is.
- Committed to adopt *cybersecurity best practices*:
(ref. Measure 12.1)
	+ Cybersecurity best practices are:
		* (a) strong password policies and management,
		* (b) email filtering for suspicious links and phishing attempts,
		* (c) protection of wireless networks,
		* (d) policies for untrusted removable media,
		* (e) physical intrusion prevention, 
		* (f) regular software updates and patch management, and
		* (g) more.
	+ Cybersecurity best practices are in line with:
		* *Cybersecurity technical standards*:
			- ISO/IEC 27001, 
			- NIST 800-53,
			- SOC 2,
			- European harmonized standard on cybersecurity (if available).
		* *Regulations*:
			- NIS2 Directive,
			- Cyber Resilience Act.
- Committed to implement the *security assurance measures*.
(ref. Measure 12.2)
	+ Security assurance measures are:
		* (a) frequent security reviews by an accredited third party,
		* (b) frequent active red-teaming,
		* (c) secure communication channels for third parties to report security issues,
		* (d) competitive bug bounty programs to encourage public participation in security testing,
		* (e) clear and public security whistleblower policies which prohibit retribution,
		* (f) installation of Endpoint Detection and Response (EDR) and Intrusion Detection System (IDS) tools on all company devices and network components,
		* (g) the use of a security team to monitor for EDR alerts and perform incident handling, response and recovery for security breaches in a timely manner, and
		* (e) more.
	+ Security assurance measures are in line with:
		* *Cybersecurity technical standards*:
			- NIST 800-53 (already mentioned):
				+ CA-2(1),
				+ CA-8(2),
				+ RA-5(11),
				+ IR-4(14).
			- NIST SP 800-115 5.2.
- Committed to implement measures to protect *storage* of model weights and associated assets:
(ref. Measure 12.3)
	+ Measures to protect storage of model weights and assets are:
		* (a) a registry of all devices and locations where model weights are stored,
		* (b) access control and monitoring of access on all devices storing model weights, with alerts on copying to non-controlled devices,
		* (c) storage on dedicated devices which host only data, code, and services treated with equivalent levels of sensitivity and security,
		* (d) ensuring model weights are always encrypted in storage and transport, with at least 256-bit security and with encryption keys stored securely on a Trusted Platform Module (TPM),
		* (e) ensuring model weights are only decrypted for legitimate use to non-persistent memory,
		* (f) implementing confidential computing once available and practical, using hardware-based, attested trusted execution environments to prevent unauthorised access to model weights while in use,
		* (g) restricting physical access to data centres and other sensitive working environments to required personnel only, along with regular inspections of such sites for unauthorised personnel or devices, and
		* (h) more.
	+ Measures to protect storage of model weights and assets are in line with:
		* *Cybersecurity technical standards*:
			- NIST 800-53 (already mentioned).
- Committed to implement measures to harden *interfaces and access control* to model weights:
(ref. Measure 12.4)
	+ Measures to harden interfaces and access control to model weights are:
		* (a) explicitly authorising only required software and personnel entities for both direct or indirect access to model weights, enforced through multi-factor authentication mechanisms, and audited on a regular basis,
		* (b) thorough review by a security team of any software interface accessing model weights for vulnerabilities or data leakage,
		* (c) hardening interfaces with access to the weights, to reduce the risk of data and weight exfiltration, using methods such as output rate limiting,
		* (d) limiting the number of people who have non-hardened direct access to weights, and
		* (e) more.
	+ Measures to harden interfaces and access control to model weights are in line with:
		* *Cybersecurity technical standards*:
			- NIST 800-53 (already mentioned),
			- NIST SP 800-171 (NISP SP 800 already mentioned),
			- INCITS 359-2004.
- Committed to implement measures to screen for and protect against insider threats:
(ref. Measure 12.5)
	+ Measures to screen for and protect against insider threats are:
		* (a) background checks on employees and contractors that have or might reasonably obtain access to unreleased model weights, associated assets, or systems that control the storage or use of unreleased model weights,
		* (b) the provision of training on recognising and reporting insider threats,
		* (c) more.
	+ Measures to screen for and protect against insider threats are in line with:
		* *Cybersecurity technical standards*:
			- NIST 800-53 (already mentioned):
				+ PM-12,
				+ PS-3.
- Committted to apply all security measures to all versions and copies of unreleased model weights and associated assets for throughout the entire model *lifecycle*. Throught the entire lifecycle means from before training to either secure deletion of weights or open releasing them,
(ref. Measure 12.6)

- Committed to ensure that any publicly available copy of the Framewrok and the Model Report doesn't disclose security mitigations to the level of detail undermining effectiveness of security mitigations. The allowed level of detail is the level of what is anyway publicly available.

## Materials to study:
- **Securing AI Model Weights: Preventing Theft and Misuse of Frontier Models** (A Playbook for Securing AI Model Weights that introduces SL1-SL5 benchmarks),
- **NIST 800-53** (main source of cybersecurity technical standards):
	+ Relevant parts:
		* Cybersecurity best practices - all,
		* Security assurance measures - CA-2(1), CA-8(2), RA-5(11), IR-4(14),
		* Measures to protect storage of model weights and associated assets - all,
		* Measures to harden interfaces and access control to model weights - all,
		* Measures to screen for and protect against insider threats - PM-12, PS-3
- Cybersecurity technical standards other than NIST 800-53 (ISO/IEC 27001, SOC 2, European harmonized standard on cybersecurity),
- Regulations (NIS2 Directive, Cyber Resilience Act),
- Cybersecurity technical standarts with focus on security assurance other than NIST 800-53 (NIST SP 800-115 5.2),
- Cybersecurity technical standarts with focus on interfaces and access control to model weights other than NIST 800-53 (NIST SP 800-171, INCITS 359-2004),
- MITRE,
- SoTA for adopting each (if relevant) of the cybersecurity best practices,
- SoTA for implementing each (if relevant) of the security assurance measures (paper: **Automated Red Teaming with GOAT: the Generative Offensive Agent Tester**, other Generative AI papers, papers from Seminari),
- SoTA for implementing each (if relevant) of the measures to protect storage of model weights and assosiated assets,
- SoTA for implementing each (if relevant) of the measures to harden interfaces and access control to model weights,
- SoTA for a secure model copying and versioning,
- Research on what can be "more" in each of the lists.

## Next step:
- Study "Securing AI Model Weights: Preventing Theft and Misuse of Frontier Models".
