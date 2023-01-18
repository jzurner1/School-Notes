Google dorking is that utilization of Google's advanced search tools to find custom content. This is also called Google hacking and can be used for recon.

# GHDB
The Google Hacking Database is a database that contains a massive list of [[Google dorking|Google dorks]] that can be used to find a variety of information. This information can range from password files to error messages, and it is useful to do some basic research on an organization.

# General Google dorks
| Filter     | Example           | Description                                                                                    |
| ---------- | ----------------- | ---------------------------------------------------------------------------------------------- |
| `site`     | `site:yahoo.com`  | Only return results from specified websites                                                    |
| `inurl`    | `inurl:admin`     | Only return results with specific word in the URL. For multiple words, use `allinurl`          |
| `filetype` | `filetype:pdf`    | Return results that have a particular file extension                                           |
| `intitle`  | `intitle:admin`   | Only return results with specific word in title. For multiple words, use `allintitle`          |
| Quotations | `"will smith"`    | Only return results that exactly match the string                                              |
| Minus sign | `-actor`          | Hide results with the specified word                                                           |
| `intext`   | `intext:password` | Only return results with specific word in the entire page. For multiple words, use `allintext` |
| `ext`      | `ext:pdf`         | Similar to `filetype`                                                                                               |

### FTP server dorks
As an alternative to [[FTP search engine|FTP search engines]]:
- `inurl:github.com intext:.ftpconfig -issues` - FTP server credentials on GitHub
- `type:mil inurl:ftp ext:pdf | ps` - Sensitive directories
- `intext:pure-ftpd.conf intitle:index of` - Exposed pure-ftpd config files
- `intitle:"index of" intext:sftp-config.json` - List of FTP passwords
- `inurl:"ftp://www." "index of /"` - Various online FTP servers


Useful filetype:
- log
- txt
- en