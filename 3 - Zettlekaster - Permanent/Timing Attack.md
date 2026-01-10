Date: 2025-07-24
Tags: [[security]]

In a sign-in steps:
- find the user by login (100ms)
- decode password (50ms)
- check if the password is valid (1ms)

Even with same error returned when password or login wrong, the attacker can note the slightly difference between login exception and password exception. So a common practice is to add a timeout to login fails, to difficult this difference comparison. 