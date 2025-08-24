#  StackMarket - Decentralized Data Marketplace Smart Contract

A Clarity smart contract for a decentralized data asset marketplace built on the Stacks blockchain. This platform allows users to list, purchase, and retrieve access to tokenized data assets, while ensuring security, transparency, and fee-based revenue sharing with the marketplace owner.

---

## 📘 Table of Contents

* [Features](#features)
* [Data Structures](#data-structures)
* [Error Codes](#error-codes)
* [Functions](#functions)

  * [Public Functions](#public-functions)
  * [Read-Only Functions](#read-only-functions)
* [Validation & Security](#validation--security)
* [Installation](#installation)
* [Usage Examples](#usage-examples)
* [License](#license)

---

## ✅ Features

* Create and list digital data assets with metadata and access control
* Buy assets with STX and access them securely post-purchase
* Dynamic marketplace fee management
* Encrypted off-chain key storage for secure data delivery
* User profiles with transaction history and sales tracking
* Asset update and delisting capabilities

---

## 📦 Data Structures

### Maps

* **`data-asset-listings`**: Stores metadata of listed data assets.
* **`data-access-credentials`**: Contains encrypted keys for purchased assets.
* **`marketplace-user-profiles`**: Tracks sales, reputation, and last activity.
* **`marketplace-transactions`**: Logs successful purchases with timestamps.

### Variables

* **`asset-id-counter`**: Unique identifier for each new asset.
* **`marketplace-fee-percentage`**: Adjustable marketplace cut (default 2%).
* **`total-marketplace-transactions`**: Global counter of successful purchases.

---

## ❗ Error Codes

| Code   | Meaning                                          |
| ------ | ------------------------------------------------ |
| `u100` | Unauthorized: Only marketplace owner can execute |
| `u101` | Listing not found                                |
| `u102` | Asset already listed                             |
| `u103` | Insufficient STX balance                         |
| `u104` | Unauthorized access to restricted function       |
| `u105` | Invalid asset price                              |
| `u106` | Invalid input format or value                    |

---

## 🔓 Public Functions

### 1. `create-data-asset-listing`

Create and publish a new data asset.

### 2. `purchase-data-asset`

Allows buyers to purchase access to an asset. Platform fee is deducted, seller is paid, and transaction is recorded.

### 3. `retrieve-asset-access-key`

Allows verified buyers to retrieve the encrypted access key for purchased assets.

### 4. `update-asset-price`

Asset owners can update the price of their listing.

### 5. `deactivate-asset-listing`

Allows asset owners to deactivate their asset listing.

### 6. `update-marketplace-fee`

Admin function to change the marketplace's fee percentage (0–100%).

---

## 🔍 Read-Only Functions

### 1. `get-asset-listing-details`

Returns full metadata of a specific asset.

### 2. `get-user-profile`

Returns sales/reputation data for a given user.

### 3. `get-total-marketplace-transactions`

Returns the total number of asset purchases.

### 4. `get-current-marketplace-fee`

Returns the currently active platform fee percentage.

---

## 🔐 Validation & Security

* Input validation on all user-supplied strings and numbers.
* Role-based access control for admin functions.
* Buyer-only retrieval of asset access keys.
* Enforces non-zero prices and non-empty strings for asset data.

---

## 🛠 Installation

Deploy via the Clarity smart contract deployment tool of your choice (e.g., [Clarinet](https://docs.hiro.so/clarinet/get-started/installation)).

Example deployment:

```bash
clarinet deploy
```

---

## 🧪 Usage Examples

### Create Listing

```clojure
(create-data-asset-listing u1000 "Medical dataset" "healthcare" "enc_key_here")
```

### Purchase

```clojure
(purchase-data-asset u1)
```

### Retrieve Key

```clojure
(retrieve-asset-access-key u1)
```

---

## 📜 License

This project is open-sourced under the MIT License.

---
