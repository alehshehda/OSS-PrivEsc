# OSS-PrivEsc - Project Documentation

[![View PDF](https://img.shields.io/badge/View-PDF-blue?style=for-the-badge&logo=adobeacrobatreader&logoColor=white)](https://alehshehda.github.io/OSS-PrivEsc/OSS-PrivEsc.pdf)
[![Download PDF](https://img.shields.io/badge/Download-PDF-success?style=for-the-badge&logo=github&logoColor=white)](https://github.com/alehshehda/OSS-PrivEsc/releases/download/latest/OSS-PrivEsc.pdf)

Technical documentation and case-study write-ups for **Privilege Escalation and System Password Database Protection in Linux** (*Eskalacja uprawnień a ochrona systemowej bazy haseł w systemach Linux*), examining how local privilege escalation vectors affect access to `/etc/passwd` and `/etc/shadow` in Linux environments and how to mitigate them.

---

## Key Case Studies

- **Case Study 1 - Horizontal Escalation (`user1` -> `user2`):** Compromising a peer account, evaluating lateral access boundaries, and verifying why user-level compromise does not directly expose `/etc/shadow`.
- **Case Study 2 - Vertical Escalation (`user` -> `root`):** Exploiting local misconfigurations or services to obtain administrative privileges and gain full read access to system password hashes.
- **Case Study 3 - Container Breakout (`container` -> `host`):** Escaping container namespace/cgroup isolation to access host resources and comparing container vs. host `/etc/shadow` boundaries.
- **Case Study 4 - Kernel Exploitation (`ring3` -> `ring0`):** Exploiting kernel-space vulnerabilities from unprivileged user space to bypass DAC/MAC boundaries and reach full host control.

---

## Course & Authors

Project developed for the **Operating Systems Security** (*Ochrona Systemów Operacyjnych*) course at **Wrocław University of Science and Technology** (WUST / PWr), Faculty of Information and Communication Technology (Cybersecurity), **Group 4**.

| Author | Assigned Case Study | Vector |
| :--- | :--- | :--- |
| **Adam Rola** | Case Study 1: Horizontal Escalation | `user1` -> `user2` |
| **Ruslan Hedz** | Case Study 2: Vertical Escalation | `user` -> `root` |
| **Aleh Shehda** | Case Study 3: Container Breakout | `container` -> `host` |
| **Aliaksei Lapachuk** | Case Study 4: Kernel Exploitation | `ring3` -> `ring0` |

---

## Repository Structure

```text
├── main.tex                                     # Master LaTeX document
├── .github/workflows/compile.yml                # Automated PDF compilation CI pipeline
├── config/                                      # Metadata, title, theme, and optional section toggles
├── preamble/                                    # Typography, macros, tables, listings, and styling
├── frontmatter/                                 # Title page and abbreviations list
├── chapters/
│   ├── 1_wstep.tex                              # Introduction, problem statement, and methodology
│   ├── 2_podstawy_teoretyczne.tex               # Privilege model, password database, and defenses
│   ├── 3_case_study_1_eskalacja_pozioma.tex     # Case Study 1: Horizontal escalation
│   ├── 4_case_study_2_eskalacja_pionowa.tex     # Case Study 2: Vertical escalation
│   ├── 5_case_study_3_ucieczka_z_kontenera.tex  # Case Study 3: Container breakout
│   ├── 6_case_study_4_eksploatacja_jadra.tex    # Case Study 4: Kernel exploitation
│   └── 7_podsumowanie.tex                       # Comparative analysis and final conclusions
├── bib/                                         # BibTeX references (references.bib) and Polish bst style
├── images/                                      # Screenshots and diagrams (cs1/..cs4/)
└── logos/                                       # University logo assets
```

---

## Compilation

The document is automatically compiled to **`OSS-PrivEsc.pdf`** via the GitHub Actions CI pipeline (`.github/workflows/compile.yml`) on every push to `main`.
