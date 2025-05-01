# <img alt="vulnx" src="https://raw.githubusercontent.com/whoamikiddie/assets/main/logo-transparent.png" height="140" />

## vulnx Workflow

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
