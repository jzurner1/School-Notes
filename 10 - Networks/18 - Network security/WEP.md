WEP is the original standard for WLAN security. With WEP, an access point is configured with a static WEP key. Wireless clients that need to associate with an access point are configured with an identical key, making this a form of PSK security. It specifically uses a 40-bit WEP key, which is relatively weak today.

It is an alternative to WPA and WPA2.

A WEP key is a static string of characters, making it compromisable with a brute force attack. Another concern is that WEP uses RC4 as its encryption algorithm.

# RC4
RC4, pronounced arc four, uses a 24-bit initialization vector (IV), which is a string of characters added to the transmitted data such that the same plaintext data frame will never appear as the same WEP-encrypted data frame. However, the IV is transmitted in plaintext, so a malicious user can capture many packets and then use an algorithm to determine the static WEP key.

Some WEP implementations use a longer WEP (such as 128 bits instead of 40) but both the wireless clients and their access point must support the longer key.