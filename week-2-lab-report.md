# Part 1 - Server
## StringServer Code
![Code Image](week2images/stringservercode.png)

## Using `/add-message`
### `/add-message?s=Hello`
![Message 1 Image](week2images/firstmessage.png)

The first method called is the `handleRequest` method in the `StringHandler` class. The provided argument is `localhost:4000/add-message?s=Hello`, which is of type `URI` and is labeled `url`. At this point, the instance variable `message` is still at its initial value: `""`. We can then list out the next methods below:

- First `if` statement: `getPath` is called from the `url` object, it returns `"/add-message"`. Next method called is `equalsIgnoreCase` which has argument `"/add-message"`, comparing the message from `getPath` with the argument.
- Second `if` statement: `getQuery` is called from the `url` object, it returns `"s=Hello"`. Local string array `query` is created with values from splitting the query with `=`, provided by the `split` method with argument `"="`.
- Third `if` statement: compares the first string in the `query` array with `"s"` by using the `equalsIgnoreCase` method with argument `"s"`.
- Fourth `if` statement: no methods called, checks length of `query` array.
- Fifth `if` statement: instance variable `message` is checked to see if empty by using the `equalsIgnoreCase` method with argument `""`. Since this is true for this query, `"Hello"` is added to the instance variable `message`, making `message = "Hello"`. 

In the first `if` statment, the first method called is `getPath` from the `url` object, which returns the value of `"/add-message"`. This string is then compared with the `equalsIgnoreCase` method with argument `"/add-message"`.
### `/add-message?s=How are you`
![Message 2 Image](week2images/secondmessage.png)
