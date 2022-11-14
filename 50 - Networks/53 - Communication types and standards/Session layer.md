The fifth layer of the [[OSI model|OSI model]]. This layer is responsible for setting up, maintaining, and tearing down sessions.

![[Pasted image 20220822203745.png]]

The functions of the session layer are as follows:
- Setting up a session: many procedures require sessions, including:
	- Checking user credentials
	- Assigning numbers to a session's communication flows to uniquely find each one
	- Negotiating services needed during the session
	- Negotiating which device begins sending data
- Maintaining a session: this is needed in a few situations:
	- Transferring data
	- Reestablishing a disconnected session
	- Acknowledging receipt of data
- Tearing down a session: a session can be torn down either based on agreement of the devices or because one party disconnects, either intentionally or unintentionally.