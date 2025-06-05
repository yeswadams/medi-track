# MediTrack: Blockchain-Based Medical Supply Chain Management

[![GitHub license](https://img.shields.io/github/license/YourGitHubUsername/meditrack?style=flat-square)](LICENSE)
[![GitHub stars](https://img.shields.io/github/stars/YourGitHubUsername/meditrack?style=flat-square)](https://github.com/YourGitHubUsername/meditrack/stargazers)
[![GitHub issues](https://img.shields.io/github/issues/YourGitHubUsername/meditrack?style=flat-square)](https://github.com/YourGitHubUsername/meditrack/issues)
[![LinkedIn](https://img.shields.io/badge/Connect_on_LinkedIn-blue?style=flat-square&logo=linkedin)](https://www.linkedin.com/in/yourprofile/)

---

## Table of Contents

* [1. Project Overview](#1-project-overview)
* [2. The Problem](#2-the-problem)
* [3. The Solution](#3-the-solution)
* [4. Key Features](#4-key-features)
* [5. Technical Architecture](#5-technical-architecture)
* [6. Tech Stack & Core Dependencies](#6-tech-stack--core-dependencies)
* [7. Getting Started](#7-getting-started)
    * [7.1. Prerequisites](#71-prerequisites)
    * [7.2. Installation & Setup](#72-installation--setup)
    * [7.3. Configuration](#73-configuration)
    * [7.4. Running the Application](#74-running-the-application)
* [8. Smart Contract Details](#8-smart-contract-details)
* [9. Project Structure](#9-project-structure)
* [10. Usage & Demo](#10-usage--demo)
* [11. Testing](#11-testing)
* [12. Deployment](#12-deployment)
* [13. Future Enhancements & Roadmap](#13-future-enhancements--roadmap)
* [14. Contributing](#14-contributing)
* [15. License](#15-license)
* [16. Contact](#16-contact)

---

## 1. Project Overview

MediTrack is a proof-of-concept decentralized application (dApp) engineered to enhance **transparency, traceability, and trust** within the pharmaceutical supply chain. Leveraging the immutable ledger of the **Ethereum blockchain** and the decentralized storage capabilities of **IPFS**, MediTrack provides an auditable, tamper-proof record of medical products from manufacturer to patient. This project showcases a robust full-stack implementation using **Next.js** for a modern web experience, demonstrating proficiency in dApp development and secure data handling.

## 2. The Problem

The global medical supply chain is plagued by a pervasive lack of **verifiable transparency and immutable traceability**, directly facilitating the widespread proliferation of **counterfeit and substandard medications**. This systemic vulnerability poses severe threats to patient safety, erodes public trust in healthcare, and inflicts substantial financial and reputational damage upon legitimate pharmaceutical stakeholders.

* **Patient Safety Risks:** Individuals unknowingly consume ineffective or harmful counterfeit drugs, leading to adverse health outcomes and increased mortality rates.
* **Economic & Reputational Damage:** Legitimate manufacturers incur significant financial losses from diverted products and brand erosion due.
* **Operational Inefficiencies:** Distributors and healthcare providers face challenges in validating product authenticity, leading to delays and complications in inventory management and recalls.
* **Regulatory Challenges:** Authorities struggle with fragmented and opaque data, hindering effective oversight and timely enforcement actions against illicit activities.

## 3. The Solution

MediTrack addresses these critical challenges by establishing a **decentralized, verifiable, and transparent single source of truth** for medical product provenance. Every significant event in a product's lifecycle – from manufacturing and packaging to shipping, receiving, and dispensing – is recorded as an **immutable transaction on the Ethereum blockchain via Solidity smart contracts**.

This design ensures:
* **Tamper-Proof Records:** Once recorded, data cannot be altered or deleted.
* **Enhanced Trust:** All authorized participants can verify a product's complete history.
* **Streamlined Audits:** Provides an irrefutable audit trail for regulatory compliance.
* **Counterfeit Mitigation:** Significantly reduces the entry points for illegitimate medications by enabling robust authentication at every handover.

## 4. Key Features

* **Immutable Supply Chain Tracking:** Records every product movement and status change on the Ethereum blockchain via custom-built Solidity smart contracts.
* **QR Code Product Verification:** Enables quick and easy verification of a product's authenticity and history by scanning a unique QR code linked to its on-chain data.
* **Decentralized Document Storage (IPFS):** Securely stores associated off-chain documents (e.g., batch certificates, quality control reports) on IPFS, with their content hashes recorded on the blockchain for integrity verification.
* **Role-Based Access Control (RBAC):** Implements distinct permission sets for Manufacturers, Distributors, and Retailers (Pharmacies/Hospitals) to manage their respective actions and data visibility within the dApp.
* **MetaMask Wallet Integration:** Facilitates secure, decentralized user authentication and enables users to sign and broadcast blockchain transactions directly from their browser.
* **Comprehensive Product Lifecycle:** Supports tracking products through core stages including Manufacturing, Packaging, Shipment, Receipt, and Dispensing.

## 5. Technical Architecture

MediTrack employs a modern full-stack dApp architecture that leverages the strengths of both traditional web development and blockchain technologies.

```mermaid
graph TD
    A[User Interface: Next.js App] --> B(API Routes: Next.js Backend)
    B --> C{Blockchain Interaction: Ethers.js/Web3.js}
    C --> D(Ethereum Network: Infura Node)
    D --> E[Smart Contracts: Solidity]
    E -- Product History / Events --> F(On-Chain Data)
    B --> G(IPFS Client / Gateway)
    G --> H[Decentralized Storage: IPFS Network]
    H -- Document Hashes --> E
    User --> I(MetaMask Wallet)
    I -- Wallet Connect & Transaction Signing --> C
