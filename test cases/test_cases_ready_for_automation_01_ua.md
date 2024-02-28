# Example of test cases ready for automation for https://coffee-cart.app/

## Test 01.1 - Buy an espresso from the main page
**📃 Description:** Verify it is possible to buy the single cup of coffee  
**🏷️ Tags:** Smoke, Positive  
**🗝️ Preconditions:**
- User is in the main page
- Cart is empty

**👣 Steps:**
- Click on Espresso cup
- Click on Total box in the right bottom corner
- Enter payment details
  - Name. String. length > 0, all chars allowed. Example: Oleksii
  - Email. String. Must match email pattern. Example: aaa@bbb
- Click submit button

**💡 Expected Results:**
- Verify the message "Thanks for your purchase. Please check your email for payment." displayed
- Verify the cart is empty
- Verify the Total amount is $0.00

## Test 02.1 - Buy an espresso from the cart page
**📃 Description:** Verify it is possible to buy the single cup of coffee from the cart page  
**🏷️ Tags:** Positive  
**🗝️ Preconditions:**
- User is in the main page
- Cart is empty

**👣 Steps:**
- Click on Espresso cup
- Go to cart page
- Verify there is 1 item, Espresso, in the list
- Verify the total is $10.00
- Enter payment details
  - Name. String. length > 0, all chars allowed. Example: Oleksii
  - Email. String. Must match email pattern. Example: aaa@bbb
- Click submit button 

**💡 Expected Results:**
- Verify user is redirected to the main page
- Verify the message "Thanks for your purchase. Please check your email for payment." displayed
- Verify the cart is empty
- Verify the Total amount is $0.00

## Test 02.2 - Check coffee cannot be bought without invalid details
**📃 Description:** Verify it is not possible to buy the coffee if details are invalid  
**🏷️ Tags:** Negative  
**🗝️ Preconditions:**
- User is in the main page
- Cart is empty

**👣 Steps:**
- Click on Espresso cup
- Click on Total box in the right bottom corner
- Enter next pairs of payment details

| name      | email     |
|-----------|-----------|
| \<empty\> | a@b       |
| oleksii   | \<empty\> |
| oleksii   | aaa.com   |
| ol        | @         |
| o         | a@        |
- Click submit button 

**💡 Expected Results:**
- Error is displayed
- Coffee is not bought

## Test 03.1 - Check a random promo on each 3rd coffee added and decline
**📃 Description:** Verify there is a promo on ech 3rd cup in the cart (3, 6, 9...)  
**🏷️ Tags:** Positive, Promo   
**🗝️ Preconditions:**
- User is in the main page
- Cart is empty

**👣 Steps:**
- Click 3 times on coffee cups from the list: Espresso, Latte, Cappuccino, Mocha, Espresso Macchiato, Flat White, Americano
- Verify promo offer displayed
- Click "Nah, I'll skip" button
- Verify there are still 3 cups in the cart
- Click 3 times on coffee cups from the list: Espresso, Latte, Cappuccino, Mocha, Espresso Macchiato, Flat White, Americano

**💡 Expected Results:**
- Verify promo offer displayed
- Verify there are 6 cups in the cart

## Test 04.1 - Check the empty cart page
**📃 Description:** Verify there is no coffee in the empty cart  
**🏷️ Tags:** Smoke, Negative  
**🗝️ Preconditions:**
- User is in the main page
- Cart is empty

**👣 Steps:**
- Go to cart page

**💡 Expected Results:**
- Verify the cart is empty
- Verify there is a message "No coffee, go add some." displayed
