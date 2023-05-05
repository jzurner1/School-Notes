`ffuf` is a web fuzzer, usually used for brute forcing directories but useful for many parts of web application vulnerabilities. It finds endpoints using word lists.

# Installation
`ffuf` can be installed in a number of ways:
- **apt**: `sudo apt install ffuf`
- **go**: First install go with `sudo apt install golang`, then, `go get gethub.com/ffuf/ffuf`. This may give a newer version. To update it, do `go get -u github.com/ffuf/ffuf.

# Introduction
The most basic usage of `ffuf` is for finding URLs. The basic syntax of this is as follows:
`ffuf -u <URL> -w <word list>`
When specifying a URL, you should insert the word "FUZZ" into where you want to plug the words for the wordlist. For example, if you want to find a list of directories on the website yahoo.com, you might do:
`ffuf -u https://tryhackme.com/FUZZ/ -w wordlist.txt`

This command will try each individual URL that is listed. For example, if your URL is `https://tryhackme.com/FUZZ/` and your wordlist includes `admin`, `shop`, and `login`, it will list `login` as response code 200 and the others as 302.

# Options
### Recursion
Say you want to find how deep directories will go. It is impractical to run the `ffuf` command for each directory you find, then again in each of those directories, and so on. Fortunately, `ffuf` contains two flags for recursion.

To use recursion in a `ffuf` command, run the following as your command:
`ffuf -u <url>/FUZZ -w <wordlist> -recursion`
Notice that the `/FUZZ` part of the URL doesn't have another slash after it. This is important for recursion.

This is useful for finding URLs such as `https://en.wikipedia.org/wiki/Linux/media`, where multiple directories exist between the home page and the desired site.

There is also a recursion length option.

### File extensions
Often, webpages may have file extensions on them, such as `robots.txt`. This won't be found with a normal wordlist, so you have to add the extension flag:
`ffuf -u <url> -w <wordlist> -e <file extension>
For example:
`https://en.wikipedia.org/FUZZ/ -w wordlist.txt -e .bak`

### Other words besides FUZZ
Sometimes, you may want to use another keyword in the URL besides FUZZ. This is fine, but you can't use recursion with another keyword, so keep that in mind. In addition, don't add a slash after the new word.

To change the keyword:
`ffuf -u <url>/<new word> -w <wordlist>:<new word>
For example:
`ffuf -u https://en.wikipedia.org/W1 -w wordlist.txt:W1`

### Silent mode
Sometimes you won't want to print all the progress when working, just the results. That can be done with silent mode using the `-s` flag:
`ffuf -u <url> -w <wordlist> -s`

### Output
There are two different flags that can be used to specify output.

The `-of` flag can be used for many different formats such as html:
`ffuf -u https://en.wikipedia.org/FFUF -w wordlist.txt -of html`
Formats include json, ejson, html, md, csv, ecsv, and all for all formats

The `-o` flag can be used to name files created with the `-of` flag. For example:
`ffuf -u https://google.com/FFUF/ -w wordlist.txt -of html -o myHTML`

To output to a txt file, the best method is with the tee command:
`ffuf -u https://google.com/FFUF/ -w wordlist.txt | tee filename.txt`
This will both print the output and save it to the file.

