Date: 2025-08-20
Tags: [[scalability]], [[patterns]]

Service A communicating async with Service B should use events, even when this represent messages.

Service A publish to a broker, Service B subscribe to this broker, this approach creates a decouple between services, A doesn't know B exists.

This should be used for events (product purchased, user created) or commands (create product, purchase order)