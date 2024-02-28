# Example of manual test cases for testing https://coffee-cart.app/

## Test 01 - Buy an espresso from the main page
**📃 Description:** Verify it is possible to buy the single cup of coffee  
**🏷️ Tags:** Smoke, Positive  
**🗝️ Preconditions:**
- Cart is empty

**👣 Steps:**
- Click on Espresso cup
- Click on Total box in the right bottom corner
- Enter payment details. Name=Oleksii, Email=oleksii@infopulse.com
- Click submit button

**💡 Expected Results:**
- Verify the message about successfully purchase displayed
- Verify the cart is empty

## Test 02 - Buy an espresso from the cart page
**📃 Description:** Verify it is possible to buy the single cup of coffee from the cart page  
**🏷️ Tags:** Positive  
**🗝️ Preconditions:**
- Cart is empty

**👣 Steps:**
- Click on Espresso cup
- Go to cart page
- Verify there is 1 item, Espresso, in the list
- Enter payment details. Name=Oleksii, Email=oleksii@infopulse.com
- Click submit button 

**💡 Expected Results:**
- Verify user is redirected to the main page
- Verify the message about successfully purchase displayed
- Verify the cart is empty

## Test 03 - Check a random promo on each 3rd coffee added and decline
**📃 Description:** Verify there is a promo on ech 3rd cup in the cart (3, 6, 9...)  
**🏷️ Tags:** Positive, Promo   
**🗝️ Preconditions:**
- Cart is empty

**👣 Steps:**
- Click 3 times on coffee cups
- Verify promo offer displayed
- Click "Nah, I'll skip" button
- Verify there are still 3 cups in the cart
- Click 3 times on coffee cups

**💡 Expected Results:**
- Verify promo offer displayed
- Verify there are 6 cups in the cart

## Test 04 - Check the empty cart page
**📃 Description:** Verify there is no coffee in the empty cart  
**🏷️ Tags:** Smoke, Negative  
**🗝️ Preconditions:**
- Cart is empty

**👣 Steps:**
- Go to cart page

**💡 Expected Results:**
- Verify the cart is empty
- Verify there is a message that the cart is empty
