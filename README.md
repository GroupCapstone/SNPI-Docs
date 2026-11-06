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

---

## Artificial Intelligence Assistants

This section introduces three artificial intelligence assistants in detail: Muse AI, Claude AI, and Gemini AI. Each one is built by a different company, each one is designed for a different main purpose, and each one has its own version history.

### Muse AI

Muse is a personal artificial intelligence agent created by Meta. Unlike a simple chatbot that only answers questions, Muse is designed to act as a personal assistant that remembers context, works across conversations, uses tools, browses the web, manages files, and completes multi-step tasks for one person. Muse can help with writing, coding, research, planning, scheduling, and everyday organization. The Muse model family that powers it is called Muse Spark.

Muse versions:

- Muse Spark 1.0, the first Muse Spark generation
- Muse Spark 1.3, a later Muse Spark generation used for personal agent work

### Claude AI

Claude is a family of large language models and an artificial intelligence assistant created by Anthropic. Claude is known for careful reasoning, long context, strong coding ability, and detailed writing. The Claude family is organized into tiers. Haiku is the fastest and lowest cost tier. Sonnet is the balanced tier for everyday work and coding. Opus is the most capable tier for complex reasoning and large tasks.

Claude versions:

- Claude 1 and Claude Instant, March 2023, the first public release
- Claude 2, July 2023
- Claude 2.1, November 2023, with a larger context window
- Claude 3 Haiku, Claude 3 Sonnet, and Claude 3 Opus, March 2024, the first three-tier family
- Claude 3.5 Sonnet, June 2024
- Claude 3.5 Haiku, October 2024
- Claude 3.7 Sonnet, February 2025, with hybrid reasoning
- Claude Opus 4 and Claude Sonnet 4, May 2025
- Claude Opus 4.1, August 2025
- Claude Sonnet 4.5, September 2025
- Claude Haiku 4.5, October 2025
- Claude Opus 4.5, November 2025
- Claude Opus 4.6 and Claude Sonnet 4.6, February 2026
- Claude Opus 4.7, April 2026
- Claude Opus 4.8, May 2026

### Gemini AI

Gemini is a family of multimodal large language models and an artificial intelligence assistant created by Google DeepMind. Gemini was designed from the start to work with more than text alone. It can process text, images, audio, video, and code in one system. Gemini is used in Google products and in developer tools, and its tiers range from small on-device models to the most capable cloud models.

Gemini versions:

- Gemini 1.0 Nano, Gemini 1.0 Pro, and Gemini 1.0 Ultra, December 2023, the first Gemini generation
- Gemini 1.5 Pro, February 2024, with a context window of one million tokens
- Gemini 1.5 Flash, May 2024, the faster and lower cost tier
- Gemini 2.0 Flash, Gemini 2.0 Pro, and Gemini 2.0 Flash-Lite, January to February 2025
- Gemini 2.5 Pro, March 2025, a reasoning model
- Gemini 2.5 Flash and Gemini 2.5 Flash-Lite, 2025
- Gemini 2.5 Flash Image, October 2025, for image generation and editing
- Gemini 3 Pro, November 2025
- Gemini 3.1 Pro, February 2026
- Gemini 3.5 Flash-Lite, July 2026

### Summary

Muse, Claude, and Gemini represent three different directions in artificial intelligence assistants. Muse focuses on personal agent work for one person. Claude focuses on reasoning, coding, and careful long-form work. Gemini focuses on multimodal understanding across text, image, audio, video, and code. Together they show how quickly modern artificial intelligence is moving from simple chat toward capable, tool-using assistants.
