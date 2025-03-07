# Source

[Securing AI Model Weights: Preventing Theft and Misuse of Frontier Models](https://github.com/olga-sorokoletova/Security-Mitigations/blob/main/Securing%20AI%20Model%20Weights/paper.pdf)

# Scope

**Objective:** Securing model assets.[^1]\
**Type of asset:** model weights.[^2]\
**Risks:** theft, copying, and mimicry.

[^1]: **Other AI Security concerns:** 1. Protecting AI system confidentiality, integrity, and availability; 2. Guarding against misuse of legitimate API; 3. Harm mitigations after the exfiltration; 4. Development of a robust R&D agenda to expand the AI security toolkit; 5. Researching the roles of different actors in securing AI systems.
[^2]: **Other assets subject to protection:** 1. Training data; 2. Algorithmic insights; 3. Model architecture design; 4. Operational infrastructure; 5. Source code.

# Attack Vectors
### Taxonomy of Attack Vectors
Taxonomy consists of 38 [attack vectors](https://github.com/olga-sorokoletova/Security-Mitigations/blob/main/Securing%20AI%20Model%20Weights/attack%20vectors.md) relevant for the objective of securing AI model weights[^3] and divided into 9 categories, including the *AI-Specific Attack Vectors* category.

[^3]: **Attack vectors mentioned as relevant for other objectives:** 1. Training data poisoning; 2. Prompt injection unrelated to code execution.

### AI-Specific Attack Vectors
**AI-Specific Attack Vectors** $-$ attacks that target AI infrastructure and are only relevant for AI systems:
- AIMED AT CODE EXECUTION
  - 1. Discovering Existing Vulnerabilities in the Machine Learning Stack
  - 2. Intentional Machine Learning Supply Chain[^4] Compromise  
- MANIPULATING MODEL OUTPUTS
  - 3. Prompt-Triggered Code Execution (Prompt Injection)
- MODEL DERIVATION
  - 4. Model Extraction
  - 5. Model Distillation
   
[^4]: **ML Supply Chain:** 1. GPU hardware; 2. Data annotations; 3. Elements of the ML Software Stack; 4. Model.
       
### Feasibility of AI-Specific Attack Vectors
The image below represents assessments of the feasibility of each AI-specific attack vector from different categories of threat actors from 1 to 5.
![Feasibility of AI-Specific Attack Vectors](https://github.com/olga-sorokoletova/Security-Mitigations/blob/main/Securing%20AI%20Model%20Weights/ai-specific%20attack%20vectors%20feasibility.png)

### Security Mitigations
### Taxonomy of Security Measures
Taxonomy of all[^5] security measures relevant for the objective of securing AI model weights across all Security Levels/Benchmarks (SL1-SL5)[^6] can be found in the source paper (***pp. 95, Appendix C, Table C.1: Summary of Security Measures Across Levels***). It is divided into 10 categories, including the *AI Model Resilience* category.

[^5]: **Mitigations that are not included because they have little evidence of effectiveness, but they can be useful in some cases:** 1. Model Pruning; 2. Network Distillation.
[^6]: **Security Level 3 (SL3):** A system that can likely thwart cybercrime syndicates or insider threats (OC3), a Security Benchmark, referenced by General-Purpose AI Code of Practice as RAND SL3 benchmark that AI providers are committed to follow: *Signatories commit to implementing security mitigations designed to thwart attempts to obtain such weights and associated assets by highly motivated and well-resourced non-state actors, including insider threats, in
line with the RAND SL3 benchmark*, Commitment 12. Security mitigations.

### AI-Specific Security Mitigations (AI Model Resilience)
- MODEL ROBUSTNESS
  - 1. Input Reconstruction (Adding pre-prompt or random noise to the user prompt)
  - 2. Adversarial Training (Adding adversarial examples to the training dataset)
  - 3. Adversarial Input Detection (Classifier AI model that checks whether the user input is adversarial)
  - 4. Adversarial Output Detection (Classifier AI model that checks whether the output is the result of malicious activity) 
- ORACLE PROTECTION
  - 5. Limitations on the number of inferences using the same credentials
  - 6. Output Reconstruction (outputs are randomly modified after inference)
  - 7. Constant inference time (so that computation running time doesn't depend on the weights' values) 

# Insights from Expert Opinions

**1. Confidential computing** (*Security During Transport and Use* section of SL4) $-$ a technique for securing data while in use by ensuring a hardware-based trusted execution environment (TEE), is used to secure the weights. The use of confidential computing in GPUs is still nascent and may not be production-ready, but it is an important remark because of an overwhelming consensus by experts regarding its importance. Because confidential computing is a broader paradigm that can be used for a variety of security goals, it is important that it is implemented to provide the model weights with sufficient confidentiality.

**2. Model Extraction:** expert opinions vary widely in how plausible they think it is to infer the model weights from examining enough query responses, ranging from very easy to obviously infeasible. Clearly, more research is needed on this front.

# Literature
### Reports of AI-Specific Attacks and Vulnerabilities
- NVIDIA, “Product Security"
- NIST, “CVE-2023-7018 Detail,” National Vulnerability Database, last modified December 29, 2023d
- Oligo, “ShellTorch”
- Fred Bals, “CVE-2017-5638: The Apache Struts Vulnerability Explained,” Synopsys, September 13, 2017
- Sead Fadilpašić, “PyTorch Hit by Severe Security Compromise,” TechRadar, January 3, 2023
- Shweta Sharma, “Frequent Critical Flaws Open MLFlow Users to Imminent Threats,” CSO, January 18, 2024
- NIST, 2023d (Code execution vulnerability in Hugging-Face’s Transformers)
- TensorFlow, “Using TensorFlow Securely,” GitHub
- MITRE, “Compromised PyTorch Dependency Chain,” incident date of December 25, 2022b
- MITRE, “Arbitrary Code Execution with Google Colab,” incident date of July 2022a
- Avi Lumelsky, Guy Kaplan, and Gal Ebaz, “ShadowRay: First Known Attack Campaign Targeting AI Workloads Actively Exploited in the Wild,” Oligo, March 26, 2024
- MITRE, “Achieving Code Execution in MathGPT via Prompt Injection,” incident date of January 28, 2023
- Rich Harang, “Securing LLM Systems Against Prompt Injection,” NVIDIA, blog post, August 3, 2023
- Nicholas Carlini, Daniel Paleka, Krishnamurthy Dvijotham, Thomas Steinke, Jonathan Hayase, A. Feder Cooper, Kath-
erine Lee, Matthew Jagielski, Milad Nasr, Arthur Conmy, et al., “Stealing Part of a Production Language Model.” arXiv, arXiv:2403.06634, March 11, 2024
- Microsoft Azure (azure), “counterfit,” GitHub: "model inversion" for Model Extraction and "functional extraction" for Model Distillation
- Billy Brumley, A3/A8 & COMP128, T-79.514 ”Special Course on Cryptology,” Helsinki University of Technology, November 11. 2004
- Subhabrata Mukherjee, Arindam Mitra, Ganesh Jawahar, Sahaj Agarwal, Hamid Palangi, and Ahmed Awadallah, “Orca: Progressive Learning from Complex Explanation Traces of GPT-4,” arXiv preprint 2306.02707, June 5, 2023
- Will Knight, “A New Attack Impacts Major AI Chatbots—and No One Knows How to Stop It,” Wired, August 1, 2023
- Florian Tramèr, Fan Zhang, Ari Juels, Michael K. Reiter, and Thomas Ristenpart, ”Stealing Machine Learning Models via Prediction APIs,” 25th USENIX Security Symposium, August 10–12, 2016

### Referenced Security Frameworks
- **NIST, The NIST Cybersecurity Framework 2.0**, NIST CSWP 29 (Initial Public Draft), August 8, 2023c
- **MITRE ATT&CK** (MITRE, “ATT&CK”) and the **MITRE ATT&CK Enterprise Matrix** (MITRE, “ATT&CK—Enterprise Matrix”)
- **MITRE, “ATLAS”**
- Alina Oprea and Apostol Vassile, Adversarial Machine Learning: A Taxonomy and Terminology of Attacks and Mitigations, National Institute of Standards and Technology, NIST AI 100-2 E2023 (Initial Public Draft), March 8, 2023
- BIML, “BIML Interactive Machine Learning Risk Framework”
- Microsoft, “Failure Modes in Machine Learning,” November 2, 2022
- International Society of Automation, “The World’s Only Consensus-Based Automation and Control Systems Cybersecurity Standards,” ISA-IEC 62443 Series of Standards
- NIST, Security Requirements for Cryptographic Modules, Federal Information Processing Standards Publication 140-3, March 22, 2019
- Supply-chain Levels for Software Artifacts
---
- Anthropic, “Anthropic’s Responsible Scaling Policy,” company announcement, September 18, 2023
- OpenAI, Preparedness Framework (Beta), December 18, 2023



