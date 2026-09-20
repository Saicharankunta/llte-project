# Low-Latency Trading Engine

A C++ backend system that simulates the core order-processing workflow of a stock exchange, focusing on fast order handling, order matching, and persistent storage.

## Overview

The system models the flow of a trading order from submission to execution:

```text
Trader
  ↓
Order Request
  ↓
Order Processing
  ↓
Order Book
  ↓
Matching Engine
  ↓
Trade Execution
  ↓
Database
```

The main objective is to understand how a trading backend can process buy and sell orders efficiently while maintaining correct order-book state.

## Core Features

* Buy and sell order management
* Order book representation
* Price-based order matching
* Order creation and processing
* Trade execution
* Database persistence
* C++ implementation focused on performance
* Modular separation of trading components

## Matching Logic

The engine maintains buy and sell orders and attempts to match compatible orders based on price.

For example:

```text
Buy:
₹100 × 10 shares

Sell:
₹99 × 5 shares
```

Since the sell price is compatible with the buy price, the engine can execute a trade for the available quantity.

The remaining quantity stays in the order book.

## Technology Stack

* **C++**
* **STL containers**
* **Multithreading / synchronization**
* **SQL database**
* **Makefile**

## Project Structure

```text
.
├── *.cpp
├── *.hpp
├── headers.hpp
├── makefile
└── ...
```

The source files are separated into components responsible for order handling, matching, and supporting functionality.

## Learning Objectives

This project focuses on understanding:

1. Order-book data structures
2. Matching-engine logic
3. Efficient C++ programming
4. Thread synchronization
5. Queue-based order processing
6. Database persistence
7. Backend architecture for trading systems

## Example Order Flow

```text
BUY  → Create Order
     → Add to Order Book
     → Check SELL Orders
     → Match Compatible Orders
     → Execute Trade
     → Update Remaining Quantity
     → Persist Result
```

## Future Improvements

Possible extensions include:

* WebSocket-based order submission
* Lock-free queues
* More advanced concurrency
* Market orders
* Limit orders
* Order cancellation
* Trade history
* Performance benchmarking
* Latency measurements
* Risk checks
* Improved database optimization

## Disclaimer

This project is an educational trading-system implementation and is not intended for real-world financial trading or production exchange infrastructure.
