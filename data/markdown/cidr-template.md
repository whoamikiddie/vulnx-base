<p align="center">
  <br />
  <br />
  <strong>Execute Summary Generated by vulnx {{Version}} at <em>{{CurrentDay}}</em></strong>
</p>

## 📊 Scan Information 

<scanInfo />

***

## 🔍 Port Scan

### 🚪 Open Ports with Service Fingerprints

<content src="{{Output}}/portscan/detail-open-ports.txt" />

### 📡 Nmap Scan Results

<content src="{{Output}}/portscan/nmap-raw-{{Workspace}}.txt" shorten=true/>

***

## 🌐 HTTP Services

<content src="{{Output}}/portscan/beautify-http-{{Workspace}}.txt" />

***

## 🐞 Vulnerability Assessment

### 📋 Vulnerability Reports

- [**{{Workspace}}-report.html**]({{Output}}/vuln/active/{{Workspace}}-report.html)
- [**{{Workspace}}-sensitive.html**]({{Output}}/vuln/sensitive/{{Workspace}}-sensitive.html)
- [**{{Workspace}}-nuclei.html**]({{Output}}/vuln/nuclei/{{Workspace}}-nuclei.html)

### 🔒 Jaeles Scan Results

<content src="{{Output}}/vuln/active/jaeles-summary.txt" />

<content src="{{Output}}/vuln/sensitive/jaeles-summary.txt" />

***

### 🎯 Nuclei Scan Results

<content src="{{Output}}/vuln/nuclei/{{Workspace}}-nuclei-scan.txt" />

***

## 📂 Content Discovery

<content src="{{Output}}/directory/unique-beautify-{{Workspace}}.txt" />

***

