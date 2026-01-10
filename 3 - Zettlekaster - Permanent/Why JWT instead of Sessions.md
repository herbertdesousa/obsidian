Date: 2025-08-02
Tags: [[security]]

Sessions are powerful, [[How cookies works]] explains more about them. Being stateless, the main contra is:
- Every session sent thought request, needs to be searched in a data source, e.g.: map database
So each request takes overhead to search customer information. Instead, JWT carries the user payload in each request, but tradeoff is obviously more information over network and also, it's not encrypted, be aware of that.