# restaurant-orders
[Codecademy](https://www.codecademy.com/learn) [TypeScript](https://www.typescriptlang.org/) project.

## Restaurant Orders
Let’s come back to the restaurant recommender. The restaurant managers gave feedback that they were looking for additional functionality to filter orders so they can highlight their specials on the app.

We’re going to build on top of the previous project to filter orders instead of restaurants. The restaurant managers want to surface dishes that fit within the customer’s budget and show the cost of each dish. The program will use array methods, functions, and practice good code hygiene and organization. Let’s work on it step by step and enjoy some chicken and waffles at the end!

Your finished program will filter orders by price and print out the orders and their prices like below:
```js
Restaurant Name #1
- Order 1: $9.99
- Order 2: $8.99
Restaurant Name #2
- Order 1: $17.99
- Order 2: $15.99
```
Throughout the project, you may find it helpful to validate your progress. There are tasks at the end of each group to walk you through this, however, here are a couple of commands that may be useful as you work:

To verify your code with the typescript compiler: tsc

To run your code after you’ve compiled: node index.js

## Tasks
### Getting Started
1. Let’s look at the code again. This is a bit different than in the previous project. What do you notice about the relationship between orders.ts and restaurants.ts?

Look at the commented-out code at the bottom of index.ts to see an example of what the restaurant managers are looking for. One of the parameters to filter the orders is a value of the enum PriceBracket. You can find the definition of PriceBracket in orders.ts.

For this project, you will also need to use type aliases. There are type aliases in orders.ts and restaurants.ts. What does each alias represent?

2. Run the TypeScript compiler using the tsc command and fix any issues that may be present in the existing code.

### Using PriceBracket
3. Let’s look at the commented-out code at the bottom of index.ts to see an example of what the restaurant managers are looking for. One of the parameters to filter the orders is a PriceBracket. Orders have a discrete price associated with them though, so how do we map the PriceBracket to a maximum price?

Define a function getMaxPrice() in index.ts that given a PriceBracket returns the maximum price based on the comments in orders.ts. You can leave the implementation blank for now.

4. Write the implementation of getMaxPrice(). We will use this function later to help us with filtering orders by price.

For each value of the PriceBracket enum you should return the respective value:

- Low: 10.0
- Medium: 20.0
- High: 30.0

5. Run the TypeScript compiler to check if there are any issues that need to be fixed.

### Filtering Orders
6. Now that we have a function that will determine the maximum price for a given PriceBracket, we need to filter the orders from each restaurant that cost below that maximum price.

Define a function to get the filtered orders getOrders(). You can leave the implementation blank for now. This function takes two parameters:

- A max price value (price) from the PriceBracket enum type
- A two-dimensional list of orders (orders) using the type alias Order.

The getOrders() function will return a two-dimensional list of the same type as orders.

7. Inside getOrders(), declare a new two-dimensional array of the type alias Order called filteredOrders. Initialize it with an empty array. This is so that we can push orders that meet the price limit for all restaurants.

8. Next, you will need to filter through the orders using getMaxPrice() and return the list of orders that are less than or equal to the max price. Remember the relationship between restaurants and orders. For example, orders[0] are the orders for restaurant[0]. Let’s start by filtering orders[0].

Use the .filter() array method for filtering the orders in orders[0] where price is less than the value returned from getMaxPrice().

9. The restaurant managers want this filtering for each restaurant though. Since the orders parameter is an array of arrays, you can nest the filtering logic in a .forEach() loop.

Iterate through orders and filter each element using the filter array method you previously wrote in the body of the .forEach() loop. Push the result into filteredOrders. Then return filteredOrders inside getOrders() to complete the implementation.

10. Run the TypeScript compiler to check if there are any issues that need to be fixed.

11. Let’s print the raw filtered results to verify the function getOrders() is working as expected. You can use the commented-out example call to getOrders() at the bottom of index.ts and print it using console.log().

Remember to run the typescript compiler after you make changes. To run your code at this point, use the command node index.js.

You should see something like the following printed to the console:
```js
[
  [
    {
      name: "Gyoza and Rice",
      price: 7.99,
    },
    ...
  ]
]
```

### Printing Orders
12. 😖 The printing code we used to verify our filter function doesn’t make it easy to see the results, does it? Let’s write a function to print out the orders in a prettier format.

We’ll start with writing the function header for printOrders(). The first parameter is an array of the type alias Restaurant from restaurants.ts. The second is a two-dimensional array of the type alias Order that contains the filtered orders returned from getOrders().

13. The restaurant managers would like users to see the orders for each restaurant in the following format:
```js
Restaurant Name #1
- Order 1: $9.99
- Order 2: $8.99
Restaurant Name #2
- Order 1: $17.99
- Order 2: $15.99
```
If there are no orders for a restaurant, the app should skip printing out the name of the restaurant.

Start by printing out each eligible restaurant name using a .forEach() loop inside printOrders(). If the restaurant doesn’t have any eligible orders, do not print it out.

14. For each eligible restaurant, print out each order and it’s price. You will need to use another .forEach() loop inside the one you previously wrote for printOrders()

15. Run the TypeScript compiler to check if there are any issues that need to be fixed. When you’re ready, try using the commented-out code at the bottom of index.ts to test out your solution.

Wow, this project made me hungry! Let’s give Nikko’s a call and put in an order for Chicken and Waffles. Bon Appetit!