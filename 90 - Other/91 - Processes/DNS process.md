## Step 1: Local

1. On your computer, you decide to browse to a website, such as `xyz.com`
2. You enter the URL into a web browser and press enter
3. Your computer checks your browser's local cache, the computer's local cache, and the local configuration file
4. If nothing is found, your computer will send a query to a DNS recursive resolver

![[DNS1.png]]

## Step 2: DNS recursive resolver
1. The DNS recursive resolver receives the DNS query from your computer
2. The recursive server checks its local cache to see if it has the IP address of `xyz.com`
3. If it doesn't, it will send a request to a root name server

![[DNS2.png]]

## Step 3: Root name server
1. The root name server receives the DNS query from the recursive server
2. The root server will look through its information and retrieve the details of the top level domain (TLD), in this case `.com`, specifically where the `.com` name servers are
3. The root name server will return a list of TLD servers to the recursive resolver

![[DNS3.png]]

## Step 4: TLD server
1. The DNS recursive resolver will receive the list of TLD servers from the root name server, then send a query to a TLD server
2. The appropriate TLD server will respond to the DNS recursive resolver with the specific authoritative name server

![[DNS4.png]]

## Step 5: Authoritative name server
1. The DNS recursive resolver will receive the address of the specific authoritative name server and send a query to it
2. The authoritative name server will look in its records for the DNS record of `xyz.com`
3. It will return the DNS record to the DNS recursive resolver, which will store the record in its local cache

![[DNS5.png]]

## Step 6: Local
1. The DNS recursive resolver will forward the DNS record to your local computer
2. Your computer will store the record in its local cache for future use

![[DNS6.png]]

## Step 7: Web server
1. Your computer will send a request to the appropriate IP address that represents the URL that was entered, in this case `xyz.com`

![[DNS7.png]]