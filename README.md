# asyncawait

# `async/await` and `.then()` in JavaScript in simple terms with code examples:

# .then():

`.then()` is a method used to handle asynchronous operations in JavaScript, particularly when working with Promises. It allows you to specify what to do when a Promise is resolved (successfully completed) or rejected (encountered an error).

Imagine you're waiting for a friend to bring you some groceries. When your friend returns, you want to either cook a meal if they brought the ingredients successfully or order takeout if they didn't. `.then()` helps you do just that.

Here's a simple example:

```javascript
function bringGroceries() {
    return new Promise((resolve, reject) => {
        // Simulating fetching groceries
        const success = Math.random() < 0.5; // Random success or failure
        if (success) {
            resolve("Groceries successfully brought!");
        } else {
            reject("Sorry, couldn't find the groceries!");
        }
    });
}

bringGroceries()
    .then(message => {
        console.log(message); // Successful scenario
        // Cook meal
    })
    .catch(error => {
        console.error(error); // Error scenario
        // Order takeout
    });
```

In this example, `.then()` is used to handle the successful case when groceries are successfully brought, and `.catch()` is used to handle the error case when groceries couldn't be found.

# async/await:

`async/await` is a more recent addition to JavaScript for handling asynchronous operations in a more synchronous-looking way. It allows you to write asynchronous code that looks like synchronous code, making it easier to read and understand.

Imagine you're waiting for your friend to bring you some books from the library. Instead of continuously checking if your friend has returned, you decide to do other things until your friend comes back. `async/await` helps you do exactly that.

Here's how you can rewrite the previous example using `async/await`:

```javascript
async function bringBooks() {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            const success = Math.random() < 0.5; // Random success or failure
            if (success) {
                resolve("Books successfully brought!");
            } else {
                reject("Sorry, couldn't find the books!");
            }
        }, 2000); // Simulating delay for fetching books
    });
}

async function main() {
    try {
        const message = await bringBooks();
        console.log(message); // Successful scenario
        // Read books
    } catch (error) {
        console.error(error); // Error scenario
        // Watch TV instead
    }
}

main();
```

In this example, `async/await` is used to write asynchronous code that looks like synchronous code. The `await` keyword is used to wait for the Promise to be resolved, and `try...catch` is used to handle any errors that occur during the execution of the asynchronous operation.

Both `.then()` and `async/await` are used for handling asynchronous operations in JavaScript, but `async/await` provides a more concise and readable way to write asynchronous code compared to `.then()`.
