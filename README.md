# **Rust Trading Engine**

A simple, order-matching engine built in Rust, designed to handle multiple markets (trading pairs) and facilitate buy and sell orders.

---

## **Main Components**

### 1. **OrderBook**
- Stores all **buy (Bid)** and **sell (Ask)** orders for a given market.
- Orders are split into 'Bid' and 'Ask' categories.
- Each category is stored in a separate **HashMap** tied to specific price levels.

### 2. **Order**
- Represents an individual **buy (Bid)** or **sell (Ask)** order.
- Specifies the **quantity** of the order.

### 3. **Limit**
- Groups all orders at a certain price point.
- Includes methods to:
  - **Fill orders** at that price level.
  - Calculate the **total volume** of orders.

### 4. **MatchingEngine**
- The core of the engine responsible for executing trades.
- Maintains a collection of **OrderBooks**, each associated with a different trading pair.
- Offers functions to:
  - **Add new markets** (trading pairs).
  - **Place limit orders**.

### 5. **TradingPair**
- Represents two currencies for trading.
  - The **base currency** is the one being bought or sold.
  - The **quote currency** defines its price.

---

## **How It Works**

- The engine constantly checks for **matching orders** (e.g., a sell and a buy order at the same price).
- When a match is found, the orders are **filled** and removed from the **OrderBook**.
- Uses **Limit Orders** to ensure trades happen at or better than the specified price.

---

## **Usage Instructions**

To run the trading engine, follow these steps:

```bash
$ git clone https://github.com/yourusername/rust-trading-engine.git
$ cd rust-trading-engine
$ cargo run
