# Shopping Cart

The last step is to build a shopping cart. This is the part you're going to
do on your own, so you can practice what you've learned. This will require:

* Modifying the "Add to Cart" button so that it adds the product to the cart.
There is already a cart property in the global data object that you can use to
store an array of products. Don't worry about quantities. We'll just assume that
users need to add the same product more than once in order to buy multiples.

  <details><summary>click for more tips</summary>
 
  * Since the "Add to Cart" button is in ProductList, you want to work there. 
  * Use a Vue "@click" directive to add an event handler to the "Add to Cart" button. This event handler is a function, listed in the `methods` section for ProductList, that takes a product as a parameter and adds it to the global cart array.
  * Remember that the cart array is already part of the global data. Look for examples in the code of accessing products to see how to access cart.

</details>

 
* Modifying the menu so that it shows the number of items in the cart. You may
want to use a computed property in App.vue to do this.

  <details><summary>click for more tips</summary>
 
  * Since the menu is in App.vue, you want to work there. 
  * You will need to add a "script" section to this component since it doesn't have one already. Use a computed property to get the number of items in the cart. You can calculate this using the length of the array. 
  * Once you have a computed property, e.g. "numberOfItems()", then you can modify the `template` section in this component to use this property like you would any other property. e.g. {{ numberOfItems }}
  </details>

* Adding a Cart view that is viewed when the user clicks on the Cart menu item.
This view should show all the products in the cart. It should include a Remove
button to remove items from the cart. It should also show a message when the cart
is empty. Don't use the `ProductList` here since you won't have an `Add to Cart`
button. And you should make the shopping cart view look different from the product
listing so that the user is not confused.

  <details><summary>click for more tips</summary>
 
  * Take a look at how the Browse view is configured. There is a menu item in App.vue. When this is clicked (router-link), it goes to router/index.js to find the matching path for "/browse" and is configured to use the Browse.vue component to handle that path. You need to do something similar for a Cart view. Here are the general steps if you get stuck:
    1. Copy either Home.vue or Browse.vue to make Cart.vue. Modify it for the cart view including swapping the computed value to return the cart and the template to use a new component we will create in step 3 instead of the ProductList component.
    2. Add the path for Cart.Vue in the router/index.js file using the other routes as examples. 
    3. Copy the ProductList component to create a CartList component.  Be sure to change the loop to go through the cart instead of the products list.  
    4. Change the addItem button and function to a removeItem button and function.  This can be done by using an [index in the v-for loop](https://vuejs.org/v2/guide/list.html) and passing it in to the function. Look up how to use the splice() function to remove objects from a list.
    5. Add a v-if v-else to display a message when the cart is empty.
    6. Change the styling for the CartList component to make it look different from the product listing.
    </details>

## Extra Credit

If you have time and want a challenge, make the cart keep track of quantities.
Remember, each product has a unique ID. So you could search the cart to see if a product
is already there, and then add a `quantity` property to items in the cart. You could
also use an object that is indexed by property ID.

## Next Tutorial

[Installing on Digital Ocean](/tutorials/8-Installing-on-Digital-Ocean.md)
