# 📧 Email Flow Simulator

<div align="center">

![Email Flow](https://img.shields.io/badge/Email-Flow-blue) ![Educational](https://img.shields.io/badge/Educational-Tool-green) ![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white) ![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white) ![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)

**An interactive, educational tool that visually demonstrates how email travels from sender to receiver across the internet**

[Features](#-features) • [Quick Start](#-quick-start) • [How It Works](#-how-it-works) • [Controls](#-controls) • [Extensions](#-extensions)

---

</div>

## 🎯 Overview

The **Email Flow Simulator** is a front-end only educational application that helps students and developers understand the complex journey of an email message. It visualizes the complete email delivery process from SMTP submission through mail transfer agents (MTAs), delivery, and final retrieval using IMAP or POP3 protocols.

### ✨ Key Highlights

- 🎓 **Educational Focus**: Designed for learning and understanding email protocols
- 🎨 **Visual Animations**: Smooth, engaging animations showing email flow
- 📱 **Responsive Design**: Works seamlessly on desktop, tablet, and mobile devices
- 🚀 **Zero Dependencies**: Pure HTML, CSS, and JavaScript - no frameworks required
- 🔒 **Safe Simulation**: All network behaviors are simulated in-browser - no actual emails sent

---

## 🚀 Quick Start

### Prerequisites

- A modern web browser (Chrome, Firefox, Safari, Edge)
- No installation or dependencies required!

### Installation

1. **Clone or download** this repository
   ```bash
   git clone <repository-url>
   cd email-stimulation-website
   ```

2. **Open the file** in your browser
   - Simply double-click `index.html`, or
   - Right-click and select "Open with" → your preferred browser

3. **Start exploring!** 🎉

That's it! The simulator is ready to use.

---

## 📋 Features

### 🎛️ Interactive Controls

- **Send Button**: Trigger the email flow animation
- **Protocol Toggle**: Switch between IMAP and POP3 retrieval modes
- **Raw SMTP Log**: Toggle detailed SMTP command log
- **TLS Simulation**: Enable/disable STARTTLS encryption
- **Speed Slider**: Control animation speed (1x to 10x)
- **Pause/Resume**: Control animation playback
- **Step Through**: Advance animation step-by-step
- **Reset**: Clear current simulation and start fresh

### 📤 Sender Panel

- Complete email form (From, To, Subject, Message)
- Attachment simulation toggle
- SMTP protocol explanation with port information
- Authentication concept visualization

### 🌐 Network Pipeline

- **Visual Flow**: Animated envelope moving through nodes
  - SMTP Client
  - Outgoing MTA
  - Internet
  - Incoming MTA
  - Delivery Agent
- **SMTP Conversation**: Real-time log of SMTP commands
  - EHLO, AUTH, MAIL FROM, RCPT TO, DATA
  - Server responses (250 OK, 354, etc.)
  - STARTTLS negotiation (when enabled)
- **Status Indicators**: Visual feedback for queue states
  - Queued
  - Processing/Retry
  - Delivered
- **Timeline**: Step-by-step progress indicator

### 📥 Receiver Panel

- **IMAP Mode**:
  - Messages remain on server
  - Sync indicator
  - Server-side mailbox view
  - Client mailbox view
  
- **POP3 Mode**:
  - Messages downloaded to client
  - Removed from server after retrieval
  - Download visualization

### 📊 Detailed Logs

- **SMTP Transaction Log**: Human-friendly SMTP conversation
- **MTA Queue Events**: Mail transfer agent activities
- **Retrieval Log**: IMAP/POP3 protocol commands and responses
- **Collapsible Panel**: Expandable log viewer

---

## 🎓 How It Works

### Email Flow Journey

```
1. SMTP Submission
   ↓
   Client authenticates with SMTP server (port 587/25)
   Message submitted via SMTP commands (EHLO, AUTH, MAIL FROM, etc.)

2. MTA Queue
   ↓
   Outgoing MTA receives and queues the message
   MX record lookup for recipient domain

3. Internet Transfer
   ↓
   Message transferred across the internet to recipient's MTA

4. Delivery
   ↓
   Incoming MTA validates and queues the message
   Delivery agent places message in mailbox

5. Retrieval
   ↓
   IMAP: Client syncs with server (message stays on server)
   POP3: Client downloads message (message removed from server)
```

### Protocols Explained

#### 🔵 SMTP (Simple Mail Transfer Protocol)
- **Purpose**: Send emails from client to server
- **Ports**: 587 (TLS), 25 (non-encrypted)
- **Key Commands**: EHLO, AUTH, MAIL FROM, RCPT TO, DATA
- **Authentication**: Required for submission servers

#### 🟢 IMAP (Internet Message Access Protocol)
- **Purpose**: Access emails stored on server
- **Ports**: 993 (TLS), 143 (non-encrypted)
- **Key Features**:
  - Messages remain on server
  - Supports folders and labels
  - Syncs state across devices
  - Ideal for multiple device access

#### 🟡 POP3 (Post Office Protocol 3)
- **Purpose**: Download emails from server
- **Ports**: 995 (TLS), 110 (non-encrypted)
- **Key Features**:
  - Downloads messages to client
  - Optionally deletes from server
  - Simple, single-device access
  - Lightweight protocol

---

## 🎮 Controls

| Control | Description |
|---------|-------------|
| **Send Email** | Start the email flow simulation |
| **Pause/Resume** | Pause or resume the animation |
| **Step** | Advance animation one step at a time |
| **Reset** | Clear simulation and return to initial state |
| **Protocol Toggle** | Switch between IMAP and POP3 modes |
| **Show Raw SMTP Log** | Toggle detailed SMTP command log |
| **Simulate TLS** | Enable STARTTLS encryption in SMTP |
| **Speed Slider** | Adjust animation speed (1x - 10x) |

### ⌨️ Keyboard Shortcuts

- **Enter**: Send email (when form is focused)

---

## 🔧 Extensions

Want to extend the simulator? Here are some ideas:

### Adding New Features

1. **Error Simulation**: 
   - Modify `simulateSMTP()` to add error scenarios
   - Add new status types for error handling

2. **Additional Protocols**:
   - Extend `simulateRetrieval()` for other protocols
   - Add new protocol options in the UI

3. **Custom Messages**:
   - Enhance message formatting
   - Add HTML email support visualization

4. **Analytics**:
   - Track simulation statistics
   - Add timing information

### Code Structure

```
index.html
├── <head>
│   ├── CSS Styles (embedded)
│   └── Meta tags
├── <body>
│   ├── Header
│   ├── Controls Bar
│   ├── Main Content
│   │   ├── Sender Panel
│   │   ├── Network Pipeline
│   │   └── Receiver Panel
│   ├── Logs Panel
│   └── JavaScript (embedded)
│       ├── State Management
│       ├── Event Listeners
│       ├── Animation Functions
│       └── Protocol Simulators
```

### Key Functions

- `animateMailFlow()`: Main animation controller
- `simulateSMTP()`: SMTP protocol simulation
- `simulateIMAP()`: IMAP retrieval simulation
- `simulatePOP3()`: POP3 retrieval simulation
- `addLogEntry()`: Logging utility
- `updateTimeline()`: Timeline progress updater

---

## 📚 Educational Resources

### Learn More About Email Protocols

- **SMTP**: [RFC 5321](https://tools.ietf.org/html/rfc5321)
- **IMAP**: [RFC 3501](https://tools.ietf.org/html/rfc3501)
- **POP3**: [RFC 1939](https://tools.ietf.org/html/rfc1939)
- **STARTTLS**: [RFC 3207](https://tools.ietf.org/html/rfc3207)

### Understanding Email Flow

1. **Submission**: Client sends email via SMTP
2. **Routing**: MTA routes based on recipient domain
3. **Transfer**: Message transferred between MTAs
4. **Delivery**: Message delivered to recipient mailbox
5. **Retrieval**: Client retrieves via IMAP or POP3

---

## 🎨 Design Philosophy

This simulator prioritizes:

- **Clarity**: Easy to understand visualizations
- **Accuracy**: Realistic protocol representations
- **Education**: Explanatory text and tooltips
- **Accessibility**: Keyboard navigation and contrast
- **Performance**: Smooth animations and responsiveness

---

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. **Report Bugs**: Open an issue with detailed description
2. **Suggest Features**: Share your ideas for improvements
3. **Improve Documentation**: Help make the code more understandable
4. **Add Protocols**: Implement additional email protocols
5. **Enhance UI**: Improve visual design and animations

---

## 📝 License

This project is open source and available for educational purposes.

---

## 🙏 Acknowledgments

- Built for educational purposes
- Inspired by the need to understand email protocols visually
- Designed with students and developers in mind

---

<div align="center">

### Made with ❤️ for Education

**Happy Learning! 📚**

---

[⬆ Back to Top](#-email-flow-simulator)

</div>
.mark antony :)}
