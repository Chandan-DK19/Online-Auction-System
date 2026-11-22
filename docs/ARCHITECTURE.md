# 📐 System Architecture Specification

## Overview
The Online Auction System is architected as a modular, console-driven Java application following standard Object-Oriented Design principles.

## Module Structure

1. **`Main.java` (Controller & Presentation Layer)**:
   - Manages top-level application navigation (`do-while` menu loop).
   - Holds centralized in-memory data structures: `ArrayList<User>` and `ArrayList<Auction>`.
   - Delegates business actions to domain models.

2. **`User.java` (Identity & Authentication Layer)**:
   - Encapsulates user entity state (`name`, `username`, `password`).
   - Private attributes ensure that authentication logic is executed internally via `checkLogin()`.

3. **`Auction.java` (Core Domain Engine)**:
   - Holds listing state (`id`, `itemName`, `price`, `sellerName`, `highestBidder`, `active`).
   - Contains a dynamic collection of `Bid` objects (Composition).
   - Validates bidding rules (active check, non-seller check, price increment).

4. **`Bid.java` (Immutable Value Object)**:
   - Stores immutable bid details (`bidderName`, `amount`).

## Object Interaction Flow
```
User (Alice) ---> [Register] ---> Added to ArrayList<User>
User (Alice) ---> [Create Auction] ---> Auction created (Status: Active)
User (Bob)   ---> [Place Bid] ---> Validated ---> New Bid added to Auction
User (Alice) ---> [Close Auction] ---> Status: Closed ---> Winner Announced
```
