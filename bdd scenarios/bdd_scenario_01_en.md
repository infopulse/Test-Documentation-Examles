# Example of BDD scenarios for https://coffee-cart.app/


```gherkin
@Smoke
@Positive
Scenario: Buy an espresso from the main page
  Given User is on the main page
  And Cart is empty

  When User clicks on Espresso cup
  And User clicks on Total box in the bottom right corner
  And User enters payment details
    | Name   | Oleksii     |
    | Email  | aaa@bbb     |

  And User clicks submit button

  Then Verify the message "Thanks for your purchase. Please check your email for payment." is displayed
  And Verify the cart is empty
  And Verify the Total amount is $0.00

@Positive
Scenario: Buy an espresso from the cart page
    Given User is on the main page
    And Cart is empty
    
    When User clicks on Espresso cup
    And User goes to cart page
    And User verifies there is 1 item, Espresso, in the list
    And User enters payment details
        | Name   | Oleksii     |
        | Email  | aaa@bbb     |
    
    And User clicks submit button
    
    Then Verify user is redirected to the main page
    And Verify the message "Thanks for your purchase. Please check your email for payment." is displayed
    And Verify the cart is empty
    And Verify the Total amount is $0.00

@Positive
@Promo
Scenario: Check a random promo on each 3rd coffee added and decline
    Given User is on the main page
    And Cart is empty
    
    When User clicks 3 times on coffee cups
    And User verifies promo offer displayed
    And User clicks "Nah, I'll skip" button
    And User verifies there are still 3 cups in the cart
    And User clicks 3 times on coffee cups
    
    Then Verify promo offer displayed
    And Verify there are 6 cups in the cart

@Smoke
@Negative
Scenario: Check the empty cart page
    Given User is on the main page
    And Cart is empty
    
    When User goes to cart page
    
    Then Verify the cart is empty
    And Verify there is a message that the cart is empty
```