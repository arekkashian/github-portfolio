# Lab 03: Zero Trust Policy Profile

## Section 1: ZTA Component Definitions

This is based on the model described in the NIST document SP800-207

### Necessary components

#### Policy Engine

This is at core a trust algorithm that makes the decision to grant access to a resource. It should also keep logs of its behavior

#### Policy Administrator

This component implements authentication and authorization for a requester

#### Policy Enforcement Point

This component handles communication between the requester and a resource

### Optional Components

#### Continuous diagnostics and mitigation (CDM) system

This gathers information about the enterprise asset’s current state

#### Industry compliance system

This ensures that the enterprise remains compliant with any regulatory regime that it may fall under

#### Threat intelligence feed

This provides information from internal or external sources that help the policy engine make access decisions

#### Network and system activity logs

This does as expected, keeps logs of behavior. Should be separate from policy engine logs

#### Data access policies

These are the attributes, rules, and policies about access to resources

#### Enterprise public key infrastructure

This is responsible for generating certificates

#### ID management system

This is responsible for creating, storing, and managing user accounts and identity records

#### Security information and event management system

This collects security-centric information for later analysis

## Section 2: Core Principle Application

An example of the principle of least privilege could be applied to a water treatment facility example by making it so that access to computerized functions of the equipment be restricted only to actors who are supposed to be using them, for example the actor that sets a schedule of operation cannot turn the system off entirely, or cannot change the chemical composition of the treatment

## Section 3: Simplified Policy Table

| Policy Requirement | Condition to be met by user | Action if condition is met  |
| ------------------ | --------------------------- | --------------------------- |
| User Identity      | User must be an administrator      | Grant access  |
| Device Posture     | Device must be a specific signed application for management of HR records, making HTTPS or SSH requests | Grant access |
| Network Context    | Request must come from same network that records are hosted on | Grant access |

# Git Repository Metadata

Project: Lab 3 - Zero Trust Policy 

Filename: ZT-Policy-Profile.md

Commit Message: This commit uploads Lab 3 at https://github.com/arekkashian/github-portfolio/blob/main/ZT-Policy-Profile.md

Due Date: March 2, 2026