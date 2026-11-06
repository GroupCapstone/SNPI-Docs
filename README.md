# Enterprise Full-Stack Architecture and Documentation

## Introduction

This repository is the public documentation hub for the SNPI enterprise full-stack system. It is prepared and maintained by Group Capstone, a final-year research dissertation team. The repository collects the architecture, technical specifications, and design documentation for the system in one central place, so that team members, supervisors, examiners, and other readers can understand how the system is planned, built, and maintained without having to read the source code of every service first.

## Purpose

The purpose of this repository is to explain the system in detail. It describes what the system does, how its major parts fit together, which technologies were chosen and why, and which standards the team follows for security, quality, and delivery. It is a showcase of the architecture and a reference for the specifications, not a copy of the application code itself.

## System Overview

The SNPI system is an enterprise full-stack application. It is separated into a web portal, a headless application programming interface, and a database layer. Each part has a clear responsibility, and the parts communicate through defined contracts. This separation makes the system easier to develop, easier to test, and easier to change, because work on the user interface, the business logic, and the data storage can proceed in parallel without breaking each other.

### Web Portal

The web portal is the part of the system that people use directly in a browser. It presents the user interface, handles navigation and forms, and requests data from the application programming interface. It does not connect to the database directly. All business rules are enforced on the server side, so the portal remains a presentation layer.

### Application Programming Interface

The application programming interface is a headless service. It contains the business logic, authentication, authorization, validation, and data processing for the whole system. It exposes defined endpoints that the web portal and other approved clients can call. Because the interface is headless, the same service can support the web portal today and additional clients in the future.

### Database Layer

The database layer stores the system data in MongoDB, running as a replica set. A replica set keeps copies of the data on more than one node, which improves reliability and supports the transaction and availability requirements of an enterprise system.

## Technology Stack

- Web framework: Next.js 16 with the App Router
- User interface library: React 19
- Programming language: TypeScript across the web portal and the service
- Server framework: Express 5
- Database: MongoDB, configured as a replica set named rs0
- Architecture style: layered, service-oriented, and contract-based

TypeScript is used across the stack so that the web portal and the service share a common type language. This reduces errors at the boundaries between systems and makes large changes safer to review.

## Documentation Areas

This repository covers the following areas in detail:

- System architecture, including component diagrams and the responsibilities of each layer
- Technical specifications for the web portal and the application programming interface
- Data design, including collections, relationships, and validation rules
- Security design, including authentication, authorization, and protection of sensitive data
- Integration design, including how the parts of the system communicate
- Deployment design, including environments and release steps
- Testing approach, including how changes are verified before release

## Security Standards

Security is treated as a design requirement, not as a final step. The documented standards include authenticated access, role-based and attribute-based authorization, validation of all input, protection against common web vulnerabilities, and careful handling of secrets and personal data. Access to each function is limited to the users who need it, and sensitive actions are recorded so they can be reviewed later.

## Branch Protection and Change Control

The main branch of this repository is protected. Changes are not pushed to main directly. Every proposed modification must be submitted through a pull request, reviewed, and approved before it is merged. Pushing new commits to a branch dismisses stale pull request approvals, so an approval always refers to the exact code that will be merged. The main branch also cannot be deleted. These rules keep the published documentation stable and make every change traceable to a review.

## How Changes Are Made

1. Create a branch from main for the proposed change.
2. Make the change on that branch and commit it with a clear commit message.
3. Open a pull request that explains what changed and why.
4. Wait for review and address any comments.
5. Merge the pull request into main once it is approved.

## Audience

This documentation is written for the project supervisors and examiners who assess the dissertation, for the team members who build and maintain the system, and for any future developer who needs to understand the system before changing it. Each section is written to be read on its own, in plain language, with technical terms explained where they first appear.

## Maintenance

This repository is maintained by Group Capstone for the duration of the project. Documentation is updated whenever the architecture, the specifications, or the standards change, so that the published description always matches the system that is actually built.
