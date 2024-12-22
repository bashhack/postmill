<div align="center">

# PostMill 🏰⚔️

*A swift and reliable email testing companion for developers, inspired by the windmills of La Mancha.*

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Go Version](https://img.shields.io/github/go-mod/go-version/bashhack/postmill)](https://go.dev)
[![Release](https://img.shields.io/github/v/release/bashhack/postmill?include_prereleases)](https://github.com/bashhack/postmill/releases)

</div>

---

## Contents

- [Quick Start](#quick-start)
- [Why PostMill?](#why-postmill)
- [Installation](#installation)
- [Core Components](#core-components)
- [Command Reference](#command-reference)
- [Configuration](#configuration)
- [Integration](#integration)
- [Real-World Usage](#real-world-usage)

## ⚡ Quick Start

```bash
# 1. Desktop App (recommended)
Download PostMill.app from https://postmill.dev/download

# 2. Homebrew
brew install postmill

# 3. Direct Install
curl -L https://get.postmill.dev | sh

# Begin your adventure
postmill tilt

# Your windmill now stands ready:
# └─ SMTP: localhost:1025
# └─ Web:  http://localhost:8080
```

## 🚀 Why PostMill?

* **Simple**: One command (or click) to start
* **Portable**: Runs anywhere (CLI, desktop app or service)
* **Reliable**: Built in Go, minimal dependencies
* **Practical**: Real-time email testing
* **Delightful**: Making email testing enjoyable

## 📜 The Tale

PostMill transforms email testing from a mundane task into a well-ordered adventure. Like the steadfast windmills of La Mancha, it stands ready to capture and present your development emails with unwavering reliability.

## 🛡️ Core Components

### The Windmill (SMTP Server)

Stands watch over port `1025`, catching all development emails with grace and precision.

```bash
postmill tilt --quest-port 1025   # SMTP port
```

### Sancho (Worker Process)
The faithful companion, managing message processing and storage with steadfast reliability.

```bash
postmill tilt --sancho   # Enable verbose mode
```

### The Watch Tower (Web Interface)
Your window into the email testing realm, where captured messages are displayed with simplicity and charm.

```bash
postmill tilt --windmill-port 8080   # UI port
```

## 📦 Installation

Choose the path that suits your quest:

### Desktop Application

Download PostMill.app for your platform:

🚧 Under Construction 🚧

### Command Line

```bash
# Homebrew (macOS & Linux)
brew install postmill

# Direct download (all platforms)
curl -L https://get.postmil.dev || sh

# Go developers
go install github.com/bashhack/postmill@latest
```

## IDE Integration

🚧 Under Construction 🚧

## ⚔️ Command Reference

Begin your quest:

``` bash
# Core Commands
postmill tilt                                    # Start all services
postmill halt                                    # Graceful shutdown

# Configuration
postmill tilt --quest-port 1025                 # SMTP port
postmill tilt --windmill-port 8080              # UI port
postmill tilt --tales-path ~/postmill_data      # Storage location
postmill tilt --sancho                          # Enable verbose mode

# Tale Management
postmill tales list                             # List all emails
postmill tales watch                            # Monitor in real-time
postmill tales clear                            # Clear all
postmill tales clear --older-than 24h           # Clear with age filter

# Status Commands
postmill status                                 # Show system status
postmill status --json                          # Machine-readable status

# Development Commands
postmill tilt --watch                           # Watch mode
postmill tilt --ci                              # CI mode
```

Advanced usage:

``` bash
# Custom ports
postmill tilt --quest-port 2025 --windmill-port 8080

# Specific storage location
postmill tilt --la-mancha ~/postmill_data

# Development mode
postmill tilt --sancho --watch
```

## ⚙️ Configuration

``` yaml
# ~/.postmill.yaml
quest:
  port: 1025
  host: "0.0.0.0"

windmill:
  port: 8080
  theme: "light"  # or "dark"
  tales_per_page: 50

sancho:
  workers: 2
  wisdom: true    # verbose logging
  
la_mancha:
  scrolls: "~/.postmill/tales"
  memory: "24h"   # retention period
```

## 🔌 Integration

### Rails

``` ruby
# config/environments/development.rb
config.action_mailer.delivery_method = :smtp
config.action_mailer.smtp_settings = {
    address: 'localhost',
    port: 1025
}
```

### Django

``` python
# settings.py 
EMAIL_HOST = 'localhost'
EMAIL_PORT = 1025
EMAIL_USE_TLS = False
```

### Node.js

``` javascript
// nodemailer configuration
const transport = nodemailer.createTransport({
    host: 'localhost',
    port: 1025,
    ignoreTLS: true
    secure: false,
    tls: {
        rejectUnauthorized: false
    }
});
```

### Go

``` go
// Go stdlib
smtp.SendMail("localhost:1025", nil, 
    "from@example.com",
    []string{"to@example.com"},
    []byte("Hello!"))

// Go with gomail
d := gomail.NewDialer("localhost", 1025, "", "")
```

## 📊 Real-World Usage

### Local Development

``` bash
# Terminal 1: Start PostMill
postmill tilt --watch

# Terminal 2: Run your application
rails server  # or your app's start command

# Terminal 3: Monitor emails
postmill tales watch
```

### CI Pipeline

``` yaml
# GitHub Actions
steps:
  - name: Setup PostMill
    run: |
      curl -L -o postmill https://get.postmill.dev
      chmod +x postmill
      ./postmill tilt --ci &
```

## 📚 Documentation

* [Installation Guide]()
* [Configuration Guide]()
* [API Reference]()
* [Pro Features]()

## 🌟 Pro Features

Upgrade your quest with PostMill Pro:

* 📦 Extended message retention
* 👥 Team collaboration features
* 🔍 Advanced search capabilities
* 📊 Email analytics
* 🔗 REST API access
* 💬 Priority support

[Learn More About PostMill Pro]()

## 🤝 Contributing

Whether you're a knight of code or a squire of syntax, contributions are welcome! See the [Contributing Guide]() for details.

## 📜 License

PostMill's core functionality is available under the MIT License. See the [LICENSE](LICENSE) file for details.

Some features marked as "Pro" require a separate commercial license. For more information:
- [Commercial Licensing](https://postmill.dev/license)
- [Feature Comparison](https://postmill.dev/compare)
- [Contact Sales](https://postmill.dev/contact)

PostMill® and the PostMill logo are trademarks of Marc Alvarez.

---

<div align="center">

*"Too much complexity may be madness. And maddest of all: to see email testing as it is, and not as it should be."*

— Adapted from Don Quixote, with apologies to Cervantes

Made with ❤️ by bashhack.

</div>
