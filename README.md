# Vulnx

Vulnx is a powerful vulnerability scanning and reconnaissance tool designed for security professionals and penetration testers. It provides comprehensive scanning capabilities with parallel execution for efficient security assessments.

![Vulnx Logo](logo.svg)

## Overview

Vulnx is a next-generation security scanning platform that combines advanced reconnaissance techniques with powerful vulnerability assessment capabilities. Built with performance and extensibility in mind, it enables security professionals to conduct thorough security assessments efficiently.

The tool's modular architecture allows for easy integration of new scanning modules and custom workflows, making it adaptable to various security assessment scenarios. Whether you're conducting a quick security check or a comprehensive penetration test, Vulnx provides the tools and flexibility needed for effective security analysis.

## Installation

### Quick Start
```bash
# Clone the repository
git clone https://github.com/whoamikiddie/vulnx-base.git

# Navigate to the project directory
cd vulnx-base

# Move the binary to system path
sudo mv vulnx /usr/bin
```

## Key Features

### Scanning Capabilities
- 🔍 Parallel scanning with configurable thread management
- 🌐 Multiple workflow types for different scanning scenarios
- 🛡️ Advanced Cloudflare detection and bypass mechanisms
- 📊 Comprehensive reporting with detailed findings
- 🔄 Modular architecture for easy extension
- 🚀 High-performance scanning engine

### Security Intelligence
- Advanced fingerprinting of web technologies
- Detection of common security misconfigurations
- Identification of exposed sensitive information
- Automated vulnerability assessment
- Custom rule support for specialized scanning

### Integration Features
- REST API for automation and integration
- Webhook support for real-time notifications
- Export capabilities in multiple formats (JSON, CSV, PDF)
- Integration with popular security tools
- Custom plugin support

## Architecture

### Core Components
- **Scanning Engine**: High-performance parallel scanning core
- **Workflow Manager**: Orchestrates scanning processes
- **Module System**: Extensible plugin architecture
- **Reporting Engine**: Generates detailed security reports
- **Configuration Manager**: Handles tool settings and profiles

### Data Flow
1. Target input and validation
2. Workflow selection and initialization
3. Parallel scanning execution
4. Results collection and analysis
5. Report generation and export

### Security Features
- Rate limiting to prevent target overload
- Proxy support for anonymity
- SSL/TLS verification options
- Custom header support
- Session management

## Use Cases

### Security Assessment
- Web application security testing
- Network vulnerability scanning
- Cloud infrastructure assessment
- API security testing
- Mobile application security

### Compliance
- PCI DSS compliance scanning
- HIPAA security assessment
- GDPR compliance checking
- Industry-specific security standards

### Research
- Security research and analysis
- Vulnerability discovery
- Security tool development
- Security education and training

## Core Capabilities

### Advanced Scanning
Vulnx implements sophisticated scanning algorithms that can efficiently identify vulnerabilities across various attack surfaces. Its parallel processing capabilities ensure quick and thorough scanning of large target environments.

### Workflow Management
The platform supports multiple workflow types, allowing users to choose the most appropriate scanning strategy for their needs. From quick reconnaissance to deep vulnerability analysis, Vulnx adapts to your requirements.

### Security Intelligence
Built-in security intelligence features help identify and bypass common security measures like Cloudflare protection, enabling more effective security assessments.

### Reporting and Analysis
Comprehensive reporting capabilities provide detailed insights into discovered vulnerabilities, with clear categorization and severity assessment to help prioritize remediation efforts.

## Vulnx Workflow

Workflow is part of vulnx which is a collection of YAML files that describe your methodology.

### Basic Usage

```bash
vulnx scan -f [flowName] -t [target]
vulnx scan -m [modulePath] -T [targetsFile]
vulnx scan -f /path/to/flow.yaml -t [target]
vulnx scan --threads-hold=30 -f cidr -t 1.2.3.4/24
vulnx scan -m /path/to/module.yaml -t [target] -l /tmp/log.log
cat targets | vulnx scan -f sample
```

### Advanced Usage

```bash
vulnx scan -T list_of_targets.txt -W custom_workspaces
vulnx scan -t target.com -w workspace_name --debug
vulnx scan -f general -t sample.com
vulnx scan --tactic aggressive -f general -t sample.com
vulnx scan -f extensive -t sample.com -t another.com
cat list_of_urls.txt | vulnx scan -f urls
vulnx scan --threads-hold=30 -f cidr -t 1.2.3.4/24
vulnx scan -m ~/.vulnx/core/workflow/test/dirbscan.yaml -t list_of_urls.txt
vulnx scan --wfFolder ~/custom-workflow/ -f your-custom-workflow -t list_of_urls.txt
vulnx scan --chunk --chunk-part 40 -c 2 -f cidr -t list-of-cidr.txt
```

### Queue Usage

```bash
vulnx queue -Q /tmp/queue-file.txt -c 2
vulnx queue --add -t example.com -Q /tmp/queue-file.txt
```

### Cloud Provider Usage

```bash
vulnx provider wizard
vulnx provider validate
vulnx provider build --token xxx --rebuild --ic
vulnx provider create --name 'sample'
vulnx provider health --debug
vulnx provider list
vulnx provider delete --id 34317111 --id 34317112
```

### Cloud Usage

```bash
vulnx cloud -f [flowName] -t [target]
vulnx cloud -m [modulePath] -t [target]
vulnx cloud -c 5 -f [flowName] -T [targetsFile]
vulnx cloud --token xxx -c 5 -f [flowName] -T [targetsFile]
vulnx cloud --chunk -c 5 -f [flowName] -t [targetsFile]
```

### Health Check

```bash
vulnx health
vulnx health git
vulnx health cloud
vulnx version --json
```

### Update

```bash
vulnx update
vulnx update --vuln
vulnx update --force --clean
```

### Utils

```bash
vulnx utils tmux ls
vulnx utils tmux logs -A -l 10
vulnx utils ps
vulnx utils ps --proc 'jaeles'
vulnx utils cron --cmd 'vulnx scan -t example.com' --sch 60
vulnx utils cron --for --cmd 'vulnx scan -t example.com'
vulnx utils workflow
vulnx config set --threads-hold=10
```

## Available Workflows
- `general`: Sequential scanning
- `advance`: Parallel scanning
- `archive`: Archive scanning
- `dirbscan`: Directory scanning
- `fingerprint`: Technology fingerprinting
- `vuln`: Vulnerability scanning

## Configuration

Vulnx uses a configuration file located at `~/vulnx-base/config.yaml`. You can customize:
- API keys
- Scan parameters
- Output directories
- Module settings

## Documentation

For detailed documentation, please visit our [Documentation](README.md).

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

