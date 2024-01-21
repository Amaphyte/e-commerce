# e-commerce app


 
 // Sample product data
 const products = [
   { id: 1, name: "singlet", price: 10.99 },
   { id: 2, name: "hoodie", price: 19.99 },
   { id: 3, name: "packet shirt", price: 7.49 },
   { id: 4, name: "t-shirt", price: 12.99 },
   { id: 5, name: "vintage", price: 15.99 }
 ];
 
 // Sample cart data
 let cart = [];
 
// FUNCTION TO DISPLAY PRODUCTS 
 function displayProducts() {
   console.log("Available Products:");
   products.forEach((product) => {
     console.log(
         [`${product.id} ${product.name} $${product.price} ${product.quantity} ${product.discount}`],
     );
   });
 }


 //FUNCTION TO ADD PRODUCT TO CART
 function addToCart(productId, quantity) {
   const selectedProduct = products.find((product) => product.id === productId);
   if (selectedProduct) {
     const itemInCart = cart.find((item) => item.product.id === productId);
     if (itemInCart) {
       itemInCart.quantity += quantity;
     } else {
       cart.push({ product: selectedProduct, quantity });
     }
     console.log(`${selectedProduct.name} added to cart`);
    } else {
     console.log("Invalid product ID.");
   }
 }


 //FUNCTION TO VIEW CART
 
 function viewShoppingCart() {
    console.log("shopping cart");
    if (cart.length === 0) {
      console.log("cart is empty");
    } else {
      cart.forEach((product, index) => {
        console.log(`$ {index + 1}. ${product.name} - $${product.price}`);
      });
    }
  }
  
 
 //FUNCTION TO CHECKOUT
 function checkout() {
   let total = 0;
   cart.forEach((item) => {
     total += item.product.price * item.quantity;
   });
   console.log(`sum: $${sum.toFixed(2)}`);
   console.log("Thank you for shopping with us!");
   cart = [];
 }

 //FUNCTION TO START SHOPPING

 function startShopping() {
  while (true) {
    console.log("\nWelcome to the Console E-Commerce!");
    console.log("[1] Display Products");
    console.log("[2] Add to Cart");
    console.log("[3] View Cart");
    console.log("[4] Checkout");
    console.log("[5] Exit");
   }
  }

    

 

// Start the e-commerce application
startShopping ();
