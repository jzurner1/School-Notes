The `show interfaces` command is used to view the [[Configuring switch interfaces|configurations]] of the interfaces in a [[Switch|switch]].

Below is a list of status codes that can be used to troubleshoot:
| Line status           | Protocol status     | Interface status | Typical cause                                       |
| --------------------- | ------------------- | ---------------- | --------------------------------------------------- |
| administratively down | down                | disabled         | shutdown is enabled                                 |
| down                  | down                | notconnect       | Cable issues or neighboring device is having issues |
| up                    | down                | notconnect       | ??                                                  |
| down                  | down (err-disabled) | err-disabled     | Port security disabled                              |
| up                    | up                  | connected        | Up and working                                                    |
