<p align="center">

 <h1 align="center">Dirb</h1>
 <h3 align="center">🚀 URL Bruteforcer</h3>
<p align="center">
<img src="https://img.shields.io/badge/C-00599C?style=for-the-badge&logo=c&logoColor=white">
<img src="https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black">
<img src="https://img.shields.io/badge/mac%20os-000000?style=for-the-badge&logo=apple&logoColor=white">
<img src="https://img.shields.io/badge/Windows-0078D6?style=for-the-badge&logo=windows&logoColor=white">
</p>
</p>

## Introduction

> Dirb a tool created by Ramon Pinuaga, this repo it's a [Sourceforge](https://sourceforge.net/projects/dirb/files/) fork and fix some error.(

DIRB is a Web Content Scanner. It looks for existing (and/or hidden) Web Objects. It basically works by launching a dictionary based attack against a web server and analizing the response.

DIRB comes with a set of preconfigured attack wordlists for easy usage but you can use your custom wordlists. Also DIRB sometimes can be used as a classic CGI scanner, but remember is a content scanner not a vulnerability scanner.

DIRB main purpose is to help in professional web application auditing. Specially in security related testing. It covers some holes not covered by classic web vulnerability scanners. DIRB looks for specific web objects that other generic CGI scanners can't look for. It doesn't search vulnerabilities nor does it look for web contents that can be vulnerables.

Maybe the last try for an unlucky security analyst... :)

## Contribution

[![darkraver](https://github.com/warengonzaga.png?size=60)](http://dirb.sourceforge.net/)
[![Ankio](https://github.com/dreamncn.png?size=60)](https://github.com/dreamncn)

## Notice

DIRB is NOT a Web Spider. It doesn't follow HTML links (by now). It searches content by rules and dictionary based attacks.

DIRB is NOT a Web Downloader. It doesn't download Web Pages (by now), only test they existence for later manual analysis.

DIRB is NOT a Web Vulnerability Scanner. It does not look for bugs. But it's designed for helping in web vulnerability assessment.


## Installation

DIRB is based on libcurl so you need to install this library where autoconf can locate it. Once libcurl is installed properly you must only do:

```shell
./configure
make
```

> You can also view the [**Workflows**](https://github.com/dreamncn/dirb/blob/master/.github/workflows/cpp.yml) compilation command.

## Download

[From Release](https://github.com/dreamncn/dirb/releases)

## Usage

DIRB takes 2 main parameters, the base URL for testing and a list of wordlist files used for the attack. 

Example:
```shell
./dirb.exe http://www.test.org/ common.txt 
```

The URL must be a valid standard URL and the wordlists are simple text files 
with a word by line. It is also possible to scan subdirectories directly:

```shell
./dirb.exe http://www.test.org/html/ common.txt
```
	
	
For SSL simply include the HTTPS url:
```shell
./dirb.exe https://www.test.org/ common.txt -i
```


You can use multiple wordfiles at a time this way (separated by comma):
```shell
./dirb.exe https://www.test.org/ common.txt,spanish.txt,names.txt 
```
	

You can append different extensions to the probed words, by using the -x or 
the -X option:
```shell
./dirb.exe https://www.test.org/ common.txt -X .html,.asp,.jsp,,

./dirb.exe https://www.test.org/ common.txt -x extensions.txt
```
	
	
## Examples


+ Scan a webserver for common directories/files: (without using file 
extensions)
```shell	
./dirb.exe http://www.test.org/ wordlists/common.txt	
```


+ Scan a webserver for common directories/files: (search for PHP and HTML 
files)
```shell
./dirb.exe http://www.test.org/ wordlists/common.txt -X .php,.html	
```


+ When a file is found, try different variations: (~, .old, etc...)
```shell
./dirb.exe http://www.test.org/ wordlists/common.txt -X .php,.html -M ~,.tmp,.old,.backup,.test
```

## Logs

2022.07.31

1. Fix compilation errors

2. Use github action to automatically compile to mac, linux, windows platform programs

## License
This project is GPL2.0 licensed.


