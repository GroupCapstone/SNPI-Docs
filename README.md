# ឯកសារស្ថាបត្យកម្មប្រព័ន្ធ — SNPI School Management System (SNP-SMS)

កម្រងឯកសារបច្ចេកទេស និងស្ថាបត្យកម្មប្រព័ន្ធកម្រិតសហគ្រាសសម្រាប់ **SNPI School Management System (SNP-SMS)** ដែលរៀបចំឡើងដោយក្រុមស្រាវជ្រាវសារណាបញ្ចប់ការសិក្សា **Group Capstone**។

This repository serves as the public architectural showcase and technical specifications hub for the SNPI Enterprise School Management System.

---

## ព័ត៌មានទូទៅអំពីគម្រោង (Project Overview)

- **អង្គការ (Organization)**: [Group Capstone](https://github.com/GroupCapstone)
- **គេហទំព័រតេស្តប្រព័ន្ធ (Testing Domain)**: [https://snpis.kesararamwithdigital.tech](https://snpis.kesararamwithdigital.tech)
- **ផតថលរចនាបថ និងឯកសារ (Design Portal)**: [https://snpis.kesararamwithdigital.tech/document/design](https://snpis.kesararamwithdigital.tech/document/design)
- **ស្ថាបត្យកម្មបច្ចេកវិទ្យា (Stack)**: Next.js 16 App Router, Express 5, TypeScript, MongoDB Replica Set (`rs0`)
- **សាខាការពារ (Protected Branch)**: `main` (Branch Protection & Ruleset Enforced)

---

## សន្តិសុខ និងការការពារកូដ (Branch Protection & Quality Gates)

ឃ្លាំងកូដនេះត្រូវបានអនុវត្តគោលការណ៍ការពារសាខា (Branch Protection Rule) និង Ruleset លើ `main` branch៖
1. **Pull Request Requirement**: ការកែប្រែកូដទាំងអស់តម្រូវឱ្យឆ្លងកាត់ការត្រួតពិនិត្យ និងយល់ព្រមតាមរយៈ Pull Request។
2. **Review Dismissal**: ការ push កូដថ្មីនឹង dismiss ការ approve ចាស់ដោយស្វ័យប្រវត្តិ។
3. **Deletion Protection**: ការពារមិនឱ្យមានការលុបសាខាគោល `main` ដោយចៃដន្យ។
