# Password Management System

A group Software Engineering project that aims to provide a centralized,
secure way to manage website and application credentials. The system's
planned features include a password vault, password generation,
password-strength checking, vault search, category organization,
security alerts, and session protection.

> **Project status:** Academic project / development in progress. The
> final implementation stack and deployment configuration are to be
> confirmed by the team.

## Table of Contents

-   [Overview](#overview)
-   [Objectives](#objectives)
-   [Planned Features](#planned-features)
-   [Security Requirements](#security-requirements)
-   [System Roles](#system-roles)
-   [High-Level Architecture](#high-level-architecture)
-   [UML Diagrams](#uml-diagrams)
-   [Project Team](#project-team)
-   [Development Workflow](#development-workflow)
-   [Getting Started](#getting-started)
-   [Scope and Limitations](#scope-and-limitations)
-   [Future Enhancements](#future-enhancements)
-   [Disclaimer](#disclaimer)

## Overview

Remembering multiple account passwords can lead to weak password
choices, password reuse, or unsafe storage practices. The Password
Management System (PMS) is designed to help users manage credentials in
one protected vault.

The project is being developed as an academic Software Engineering
project. Its Software Requirements Specification (SRS) defines the
requirements and provides a baseline for design, implementation,
testing, deployment, and maintenance.

## Objectives

-   Provide a centralized vault for website and application credentials.
-   Support secure account registration, login, and logout.
-   Help users generate strong passwords and evaluate password strength.
-   Allow credentials to be searched and organized into categories.
-   Identify weak or outdated passwords through security alerts.
-   Protect vault records using authentication, authorization,
    encryption, and session controls.
-   Demonstrate the Software Development Life Cycle (SDLC), UML
    modelling, and software testing.

## Planned Features

### 1. Account and Session Management

-   Register an account with required information.
-   Validate registration data and reject duplicate account identifiers.
-   Log in and log out.
-   Create authenticated sessions and expire or lock inactive sessions.
-   Require re-authentication after session expiry or vault lock.

### 2. Password Vault

-   Add, view, update, and delete saved credentials.
-   Store details such as service/account name, username, password,
    category, URL, and notes.
-   Require confirmation before deleting a credential.
-   Mask password values by default.
-   Restrict each user to their own vault records.

### 3. Password Generator

-   Select password length and character sets.
-   Support uppercase letters, lowercase letters, digits, and special
    characters.
-   Use a cryptographically secure random source.
-   Display the generated password without automatically saving it.
-   Save a generated password only when the user explicitly chooses to
    add it to a credential.

### 4. Password Strength Checker

-   Evaluate a password against configured quality rules.
-   Display a strength classification such as Weak, Medium, Strong, or
    Very Strong.
-   Provide feedback when a password does not meet the configured
    policy.
-   Avoid storing or logging the plaintext password being tested.

### 5. Search and Category Management

-   Search credentials by service/account name or username.
-   Create, rename, delete, and list categories.
-   Assign credentials to categories and filter the vault by category.
-   Return only records belonging to the authenticated user.

### 6. Security Alerts

-   Identify credentials that fail the configured password-strength
    policy.
-   Identify outdated passwords if password-age tracking is enabled.
-   Display alerts without unnecessarily revealing password values.
-   Allow users to mark alerts as reviewed.

### 7. Administrative and Maintenance Responsibilities

-   Provide limited system administration and configuration.
-   Support development, deployment, database maintenance, testing, and
    security fixes.
-   Keep administrative access separate from users' vault contents;
    administrator privileges must not automatically expose plaintext
    vault passwords.

## Security Requirements

Security is a core requirement of the project. The implementation
should:

-   Store authentication passwords only as secure password hashes, never
    as plaintext.
-   Encrypt vault passwords and other sensitive credential values before
    persistent storage.
-   Use established cryptographic libraries rather than custom
    cryptography.
-   Enforce authentication and authorization on the server side.
-   Check record ownership for every protected vault operation.
-   Keep passwords masked by default in list and detail views.
-   Never place plaintext passwords or vault secrets in logs, URLs,
    screenshots, or error responses.
-   Keep encryption keys, database credentials, and application secrets
    out of source control.
-   Use HTTPS/TLS for deployed network communication.
-   Validate and sanitize user input on the server side.

These are requirements and design goals; they should not be interpreted
as proof that the application has already been implemented or
security-audited.

## High-Level Architecture

The SRS describes the following logical components:

  -----------------------------------------------------------------------
  Component                           Responsibility
  ----------------------------------- -----------------------------------
  User Interface                      Registration, login, dashboard,
                                      vault, password generator,
                                      settings, and alerts

  Application / Backend               Business logic, validation, CRUD
                                      operations, authorization, and
                                      session control

  Security Layer                      Authentication, password hashing,
                                      encryption, secure random
                                      generation, and session security

  Database                            Users, protected credentials,
                                      categories, and security metadata
  -----------------------------------------------------------------------

The final programming language, framework, database, cryptographic
configuration, and deployment environment are to be selected and
documented by the team.

## UML Diagrams

The repository can include the following project design artifacts:

-   **Use Case Diagram** --- actors and the system's major use cases.
-   **Class Diagram** --- key classes and relationships, including User,
    Credentials, Category, Password Service, Security Service, and Alert
    Service.
-   **Activity Diagram** --- workflow for registration, login, protected
    operations, password tools, alerts, settings, and logout.
-   **Sequence Diagram** --- interactions between the user interface,
    backend, security service, credential service, and database.

Suggested repository structure:

``` text
password-management-system/
├── README.md
├── docs/
│   ├── use-case-diagram.pdf
│   ├── class-diagram.pdf
│   ├── activity-diagram.drawio
│   ├── sequence-diagram.drawio
│   └── SRS.pdf
└── src/                 # Add application source code here
```

Update the filenames in `docs/` to match the actual files committed to
the repository. Include editable `.drawio` files when available, and
optionally add exported PNG/PDF previews.

## Project Team

This is a four-member group project.

  -----------------------------------------------------------------------
  Team Member                         Project Contribution
  ----------------------------------- -----------------------------------
  Vedika Srivastava                   Project planning, requirements,
                                      documentation, and coordination

  Teesha Sahu                         System design, UML diagrams, and
                                      design documentation

  Utkarsh Pandey                      Application development, database,
                                      and security implementation

  Udita Yadav                         Testing, quality assurance, test
                                      cases, and defect tracking
  -----------------------------------------------------------------------

These are proposed responsibility areas based on the team's SRS. The
team may update them to reflect actual contributions.

## Development Workflow

The SRS proposes a structured, Waterfall-style SDLC:

1.  **Planning** --- define the problem, scope, feasibility, and
    milestones.
2.  **Requirement Analysis** --- prepare and review the SRS.
3.  **Design** --- develop architecture, UML models, database design,
    and UI wireframes.
4.  **Implementation** --- build the application modules and integrate
    them.
5.  **Testing** --- conduct unit, integration, system, and security
    testing.
6.  **Deployment** --- configure the application and prepare setup
    documentation.
7.  **Maintenance** --- fix defects and evaluate future improvements.

## Getting Started

The final technology stack and runnable application setup are not yet
specified in the SRS. Once implementation is available, update this
section with the actual prerequisites and verified commands.

A useful setup section should include:

1.  Required language/runtime and version.
2.  Database installation and configuration.
3.  Environment variable setup using a local `.env` file or another
    protected configuration method.
4.  Dependency installation commands.
5.  Database migration or initialization steps.
6.  Application startup commands.
7.  Test execution commands.

**Do not commit real passwords, encryption keys, API keys, database
credentials, or other secrets to GitHub.** If using environment
variables, provide a `.env.example` containing placeholder values only.

## Scope and Limitations

The baseline scope described in the SRS excludes the following unless
the team explicitly approves them as future enhancements:

-   Browser extensions.
-   Cross-device synchronization.
-   Enterprise single sign-on.
-   External breach-monitoring services.
-   Biometric authentication.
-   Production-grade cloud key management.

The SRS describes an academic prototype and does not claim that the
system is a professionally audited commercial password manager.

## Future Enhancements

Possible extensions, subject to project approval and time, include:

-   Email-based recovery or notifications.
-   Protected backup and recovery.
-   Secure credential export with clear warnings.
-   Additional security testing and usability improvements.

## Disclaimer

This project is intended for academic learning and demonstration. Do not
use it to store real or highly sensitive passwords unless the
implementation has been completed, reviewed, and independently assessed
for security.

------------------------------------------------------------------------

**Institution:** KIET Deemed to be University, Ghaziabad\
**Project:** Password Management System\
**Document baseline:** Software Requirements Specification, Version 1.0
