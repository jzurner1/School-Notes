The Nmap scripting engine is a scripting engine added on to nmap. Scripts are written in the Lua language and can be used for many things from scanning for vulnerabilities to automatically exploiting them. The NSE is particularly useful for recon.

# Installing scripts
Many scripts come included in Linux and nmap, so it is important to keep everything updated:
```
sudo apt update
sudo apt install nmap
```
You can also install scripts with the wget command and a couple followup commands:
```
# the following two lines are one command
sudo wget -O /usr/share/nmap/scripts/<script-name>.nse https://svn.nmap.org/nmap/scripts/<script-name>.nse

nmap --script-updatedb  # updates the script.db file with new scripts
```
# Browsing scripts
For a list of scripts and their usage, visit [the nmap website](https://nmap.org/nsedoc/).

Scripts are stored in the `/usr/share/nmap/scripts` folder on Linux. There are a couple way to sort through all of these scripts.

The first is the the `script.db` file, which is a formatted text file containing filenames and categories for each script. This file is very long so it may be helpful to `grep` it instead of just reading it. Below is an excerpt from it.

```
Entry { filename = "acarsd-info.nse", categories = { "discovery", "safe", } }
Entry { filename = "address-info.nse", categories = { "default", "safe", } }
Entry { filename = "afp-brute.nse", categories = { "brute", "intrusive", } }
Entry { filename = "afp-ls.nse", categories = { "discovery", "safe", } }
Entry { filename = "afp-path-vuln.nse", categories = { "exploit", "intrusive", "vuln", } }
Entry { filename = "afp-serverinfo.nse", categories = { "default", "discovery", "safe", } }
Entry { filename = "afp-showmount.nse", categories = { "discovery", "safe", } }
Entry { filename = "ajp-auth.nse", categories = { "auth", "default", "safe", } }
Entry { filename = "ajp-brute.nse", categories = { "brute", "intrusive", } }
Entry { filename = "ajp-headers.nse", categories = { "discovery", "safe", } }
```

In it, you can see that each entry has a filename and categories. See the script categories later in this page. If you want to search for a specific category, you can grep it with `grep "safe" /usr/share/nmap/scripts/script.db`.

The second way to find scripts is just using the `ls` command with some fancy search methods. For example, you could do `ls -l /usr/share/nmap/scripts/*ftp*` to find any script with ftp in the name.

# Running scripts
To run a script, simply add `--script=<script name>` to a scan.