# 🚀 Postman Route Planner 🚇  
A classical planning problem solution using **Fast Downward Planner (FDR)** to coordinate postmen delivering letters in a city with roads and a metro system! 🌆  

---

## 📖 Overview  
This project models a **city logistics problem** where postmen collect letters from houses and deliver them to mailboxes. The city includes:
- **Bidirectional roads** (walkable paths) 🛣️
- **One-way metro routes** (faster travel between stations) 🚇
- **Houses** (mail sources) �
- **Mailboxes** (delivery targets) 📬
- **Postmen** (mobile agents carrying letters) 👨💼

The goal is to generate an **optimal plan** for postmen to deliver all letters efficiently, leveraging both walking and metro transportation.

---

## 🔑 Key Features
- **Scalable setup**: for multiple postmen, mails, and mailboxes 🧩
- **Hybrid movement**: Walk on roads or use directional metro routes 🚶♂️➡️🚇
- **State tracking**: Mail positions, postmen locations, and mailbox statuses 📍
- **Metro constraints**: Boarding/alighting only at designated stations 🚉
- **FDR encoding** to model transitions, preconditions, and goals 🧠

---

## 🕵️ Problem Analysis
### Domains & Variables
- **Nodes**: City points (houses, mailboxes, metro stations, etc.)
- **Postmen**: Mobile agents with dynamic locations
- **Mails**: Move between houses → postmen → mailboxes
- **State Variables**: 
  - `postmen_location`
  - `mails_position` (in mailbox, with postman, or at house)
  - `mailboxes_location`

### Postmen Actions
- **Walk**: Bidirectional on roads.
- **Metro**: One-way travel between stations only.
- **Collect Mail**: Collect mail from houses.
- **Deliver Mail**: Deliver mail to mailbox.

### Initial State Example  
- 🏠 Houses: Nodes 10, 13  
- 📮 Mailbox: Node 7  
- Ⓜ️ Metro Stations: 2, 3, 6, 7, 8  
- 🚑 Postman: Starts at Node 14  

### 🎯 Goal  
All mails must end up in **any mailbox**! ✅  

---


## 📋 Example Plan (9 Steps)  
1. 🚶 Walk from 14 → 13  
2. 📬 Collect mail  
3. 🚶 Walk → 8  
4. 🚶 Walk → 10  
5. 📬 Collect mail  
6. 🚶 Walk → 6  
7. 🚇 Take metro → 7 (mailbox station)  
8. 📮 Deliver mail  
9. 📮 Deliver mail

---

🌟 **Built with scalability in mind** – easily extendable for complex cities with more postmen, mails, and transport options!