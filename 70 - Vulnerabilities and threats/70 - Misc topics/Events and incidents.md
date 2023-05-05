An event is any meaningful change in a system's state that is both detectable and happened at a specific time. A router crashing or an email arriving is an event. It isn't inherently good or bad, but it is something that may need to be reviewed.

An incident is an event or a series of events that is unexpected, unusual, and that poses some meaningful threat to the system's functions, performance, or security. This may include a router crashing or malware being installed. Some definitions specify that an incident must be human-caused, but in general it can be the result of disasters or other nonhuman events.

# Event evaluation
Evaluating whether a security event is an incident is one of the bigger challenges of security.
- **True positive**: An event occured, and the analysis recognized it. This is a good result as even if the event isn't an incident, it can be recognized and addressed.
- **True negative**: The event was benign and triggered no alerts. This is a good result since everything is quietly working correctly.
- **False positive**: The event was benign but the analysis mistook it for a problem. This is bad and can disrupt routine functions and cost time and money.
- **False negative**: A problem occurred but the analysis mistook it for benign behavior and didn't trigger an alert. This is bad as any resulting security compromise will go unnoticed.