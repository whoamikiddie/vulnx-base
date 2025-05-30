<p align="center">
  <br />
  <br />
  <strong>Execute Summary Generated by vulnx {{Version}} at <em>{{CurrentDay}}</em></strong>
</p>

## 📊 Scan Information 

<scanInfo />

***

## 🚀 Subdomain Discovery

<content src="{{Output}}/subdomain/final-{{Workspace}}.txt" shorten=true />

***

## 🌐 HTTP Services

<content src="{{Output}}/fingerprint/beautify-{{Workspace}}-http.txt" />

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

## 🕷️ Web Crawling Results

<content src="{{Output}}/linkfinding/links-{{Workspace}}.txt" />

***

## 📂 Content Discovery

<content src="{{Output}}/directory/unique-beautify-{{Workspace}}.txt" />

***

## 🔍 Port Scan Results

<content src="{{Output}}/portscan/open-ports.txt" />

***


