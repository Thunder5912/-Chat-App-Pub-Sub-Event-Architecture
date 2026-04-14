# 🚀 Event-Driven Chat Architecture (Pub/Sub Pattern)

![HTML5](https://img.shields.io/badge/html5-%23E34F26.svg?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/css3-%231572B6.svg?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E)

A lightweight, interactive web simulation demonstrating **Event-Driven Architecture** using the **Publish-Subscribe (Pub/Sub)** design pattern. 

### 🌐 Live Demo
**Play with the interactive simulator here:** [Live on Vercel](https://chat-app-pub-sub-event-architecture.vercel.app/)

---

## 📖 Project Overview

This mini-project was built to visually demonstrate how decoupled systems communicate. Instead of clients sending messages directly to one another (which creates tightly coupled, hard-to-maintain code), they communicate entirely through a central **Event Broker**.

### Core Concepts Demonstrated
* **Decoupling:** The Publisher (sender) has zero knowledge of the Subscribers (receivers). It simply hands the message to the broker.
* **Dynamic Routing:** The Event Broker routes messages strictly based on active "Topic" subscriptions.
* **Message Dropping:** If a message is published to a topic with no active subscribers, the broker safely drops it, preventing system crashes or memory leaks.

---

## ✨ Features

1. **Interactive Publisher:** Act as a System Admin, Support Bot, or Guest to publish messages to specific topics (`General`, `Tech`, `Alerts`).
2. **The Broker Dashboard:** A real-time console that acts as the "brain" of the architecture. Watch exactly how the broker receives, evaluates, and routes (or drops) every single event.
3. **Dynamic Subscribers:** Four independent client windows (Alice, Bob, Charlie, Diana). You can toggle their subscriptions on and off in real-time to see how it affects message delivery.
4. **Zero Dependencies:** Built entirely with Vanilla JavaScript, HTML, and CSS. No external libraries were used, making the core architectural logic easy to study and understand.

---

## 🛠️ Technology Stack

* **Frontend Structure:** HTML5
* **Styling:** CSS3 (CSS Grid, Flexbox, Custom Variables)
* **Logic & Architecture:** Vanilla JavaScript (ES6 Classes)
* **Deployment:** Vercel

---

## 🧠 How the Code Works (Architecture)

The heart of the application is the `AdvancedBroker` JavaScript class. 

It maintains a state dictionary of topics and their active listeners:
```javascript
this.topics = {
    'General': { 'Alice': callbackFn, 'Charlie': callbackFn },
    'Tech': { 'Bob': callbackFn },
    'Alerts': {}
};
