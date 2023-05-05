# Overview
[[Shodan|Shodan]] is a search engine for devices connected to the internet. While the website (shodan.io) is very powerful, it is also very expensive. The command-line interface shown here has the same features, but requires some learning.

# Commands
The basic command, `shodan`, can be used to list all available commands. Below are a list of options:

### Count
The `count` command returns the number of results for a specific query in the format `shodan count <query>`. It will return a basic integer value.

For example, you could run `shodan count microsoft iis 6.0`, which would return `5310594`.

### Download
The `download` command will download the results of a query, saving each line as a JSON banner. By default, it will return 1,000 results, but this can be changed with `--limit`. This is the most common command with the CLI because it can be used to save data and parse it with the `parse` command.

For example, you could run `shodan download microsoft-data microsoft iis 6.0`.

### Host
The `host` command will show information about a given host such as where it is located, which organization owns the IP, and the open ports.

For example, you could run `shodan host 189.201.128.250`.

### MyIP
The `myip` command will simply return your internet-facing IP address. It is run as `shodan myip` and will return a result in the format of `xxx.xxx.xxx.xxx`.

### Parse
The `parse` command is used to analyze a file that was generated with the `download` command. It lets you filter out the fields that you're interested in such as the IP and ports. It will convert the JSON to CSV and is usable for pipe-ing to other scripts.

For example, you could run `shodan parse --fields ip_str,port,org --separator , microsoft-data.json.gz`.

### Search
The `search` command lets you search Shodan and view the results in a terminal-friendly way. By default it will display the IP address, port, hostnames, and data. This can be changed with `--field`.

For example, you could run `shodan search --fields ip_str,port,org,hostnames microsoft iis 6.0`  to search Microsoft IIS 6.0 and print the IP, port, organization, and hostnames.