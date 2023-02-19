GraphQL is an open-source data query and manipulation language for [[20 - Software/26 - Programming and web development/API|APIs]]. It is designed for users to be able to send a GraphQL query to an API and get exactly what was requested.

For example, imagine the following query is made to the API:
```
{
	hero {
		name
		height
		age
	}
}
```
In turn, the response would be:
```
{
	"hero": {
		"name": "Luke Skywalker",
		"height": 1.72,
		"age": 25
	}
}
```