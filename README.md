# Multi-Student Docker Compose CLI Tool

A simple command-line tool for managing Docker Compose projects in educational environments. Each student gets their own isolated port range and can create projects from templates.

## 🚀 Quick Start

==========================================================================
common services:
--------------------------------------------------------------------------
git clone https://github.com/lee-liao/multi-student-docker-cli.git
cd multi-student-docker-cli
python3 cli-tool/cli.py create-project common --template common

cd dockeredServices/common
./setup.sh










# docker-compose up -d --build
=========================================================================
backend with correct ports in .env:
--------------------------------------------------------------------------
source .venv/bin/activate
uvicorn app.main:app --host 0.0.0.0 --port 8004 --reload --log-level debug
=========================================================================
frontend:
--------------------------------------------------------------------------
npm run dev -- --port 3004





############
# pull update from github
git pull  #get update

### 1. Check Your Port Assignment
`ash
python cli-tool/cli.py show-ports
`

### 2. Create Your First Project
`ash
# Create a RAG project
python cli-tool/cli.py create-project my-rag-project --template rag

# Create an Agent project  
python cli-tool/cli.py create-project my-agent-project --template agent
`

### 3. Start Your Project
`ash
cd ~/dockeredServices/my-rag-project
docker-compose up -d
`

## 📋 Requirements

- Python 3.8+
- Docker 20.10+
- Docker Compose 2.0+

## 🛠 Installation

### Method 1: Direct Use (Recommended)
`ash
# Clone this repository
git clone <repository-url>
cd multi-student-docker-cli

# Install dependencies
pip install -r requirements.txt

# Use directly
python cli-tool/cli.py --help
`

### Method 2: System Installation
`ash
# Install dependencies and package
pip install -r requirements.txt
pip install -e .

# Use system-wide
docker-compose-cli --help
`

## 🎯 Available Commands

`ash
# Project Management
python cli-tool/cli.py create-project <name> --template <type>
python cli-tool/cli.py copy-project <source> <destination>
python cli-tool/cli.py list-projects

# Port Management
python cli-tool/cli.py show-ports
python cli-tool/cli.py verify-ports <project>

# System Status
python cli-tool/cli.py status
python cli-tool/cli.py health-check

# Maintenance
python cli-tool/cli.py cleanup
python cli-tool/cli.py security-check
`

## 📚 Available Templates

### RAG Template
- **Services**: Python app, PostgreSQL, Vector DB
- **Use Case**: AI applications with document retrieval
- **Ports**: 5 ports automatically assigned

### Agent Template
- **Services**: Python agent, MongoDB, Redis, API Gateway
- **Use Case**: AI agents with persistent state
- **Ports**: 6 ports automatically assigned

### Common Template
- **Services**: Shared infrastructure (databases, monitoring)
- **Use Case**: Shared services for multiple projects
- **Ports**: 7 ports automatically assigned

## 🔧 Common Workflows

### Create and Start a Project
`ash
# 1. Create project
python cli-tool/cli.py create-project my-chatbot --template rag

# 2. Verify ports
python cli-tool/cli.py verify-ports my-chatbot

# 3. Start services
cd ~/dockeredServices/my-chatbot
docker-compose up -d

# 4. Check status
python cli-tool/cli.py project-status my-chatbot
`

### Copy Project for Experimentation
`ash
# Copy existing project
python cli-tool/cli.py copy-project my-chatbot my-chatbot-v2

# Start the copy
cd ~/dockeredServices/my-chatbot-v2
docker-compose up -d
`

## 🚨 Troubleshooting

### Port Conflicts
`ash
# Check port usage
python cli-tool/cli.py verify-ports --all

# Optimize ports
python cli-tool/cli.py optimize-ports
`

### Docker Issues
`ash
# Check Docker status
docker version

# Health check
python cli-tool/cli.py health-check
`

### Permission Issues
`ash
# Security check
python cli-tool/cli.py security-check
`

## 📖 Documentation

For detailed documentation, see the [docs/](docs/) directory:

- [Installation Guide](docs/installation.md)
- [Usage Examples](docs/usage.md)
- [Troubleshooting](docs/troubleshooting.md)

## 🆘 Getting Help

`ash
# General help
python cli-tool/cli.py --help

# Command-specific help
python cli-tool/cli.py create-project --help

# System diagnostics
python cli-tool/cli.py health-check --comprehensive
`

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

**Version**: 1.0.0  
**For Students**: Simple, powerful Docker Compose management  
**Support**: Check docs/ directory for detailed guides
