# TruPrice - Revealing True Cost of the World

Final Project - CS 5520 Mobile App Development - Spring 2023

> Math is hard, what is 5.75 * 1.008 + 16 * 0.0175 (the price of a 16oz bubble tea plus sugar tax)?

(Actual code base is in a [private repo](https://github.com/CS5520-Seattle-Spring23/final-project-avengers))

(This page is for [presentation](/TruPrice_presentation.pdf) and [demo](https://github.com/danielyhbi/TruPrice-ios/tree/main/demo-gifs) only)

## Teammate
- Daniel Bi [danielyhbi@](https://github.com/danielyhbi)
- Bronte Li [bronteee@](https://github.com/bronteee)
- Philip Quan [deathbysora@](https://github.com/deathbysora)

All team members are crucial to product development, including initial brainstorming, wireframe design, testing, software and UI development. The team utilized many flutter features.

Bronte lead the main effort on ML/AI (model training/deployment on image recognition, augmented reality), Philip lead the effort for overall system design (I/O, infrastructure), and Daniel lead the main effort for UI (Widgets, Navigation).

## Definitions
* TruPrice: a mobile application that allows users to scan product’s price tags and receive the true price of the products, including all taxes.

![Main Page Demo](/demo-gifs/main-page-demo.gif)
![Add items to cart](/demo-gifs/add-to-cart.gif)

## Overall Description

Here is the TL;DR:

Math is hard, what is 5.75 * 1.008 + 16 * 0.0175 (the price of a 16oz :bubble_tea: tea plus sugar tax :cry: ) ?

Taxes are hard, Washington, Oregon, Texas, etc.

Currency conversion is hard, especially if you are an international student!

Controlling yourself at Costco and not spending hundreds of dollars is hard, especially if you are a broke college student!

Price tags are tricky, $199.98 is really $200!

We, at TruPrice, want to make your life easier and help you see the truth in the world, so we decided to do the math for you with no strings attached.

TruPrice is a cross-platform, augmented-reality focused, mobile application that displays an estimated total price of an item that consumer pays upon checkout. The estimated total price is determined based on local tax laws and user-imposed surcharge (for gratuity or other purpose). User could scan a price tag or menu at grocery stores or restaurants using a smartphone, and then the “true price” is displayed next to the price tag.

Additionally, TruPrice allows user to keep track multiple items in one cart that informs the total estimated cost at checkout. TruPrice also allows displays customizable price per user’s preference.

## User Characteristics

* People with financial constraints, tight budgets
* Age 18 – 45
* Live in the US
* People who shop at grocery stores frequently

## User Stories

1. As a financially conscious shopper, they would scan the price tag to see the total price of an item after tax so that they can make buying decisions on the spot.
2. As a shopper with a max spending limit on food stamp or social security, the cart feature would inform the overall cost of items so user can decide if they can keep spending or discard items. This would either meet their spending limit, or avoid over drafting their bank account. 
3. As a shopper who wants to compare past purchases, the app would inform the user if the item was purchased at a cheaper price at another grocery store, so that the shopper can decide if they want to purchase at another store.
4. As shopper who enjoys bookkeeping, the app will record the location and timestamp for item scanned or added so that they can look up, search, or sort past purchases.
5. A user travels from Portland, Oregon (where there is no sales tax) to Seattle, Washington (where the sales tax is 10%), the application detects the change in location and automatically adjusts the calculation for the total price so that they can make better decisions about purchases while they are traveling. 
6. As a person who is concerned about their digital privacy, even with the location services off, they would input a customs location or tax rate in settings. The app would display final prices according to user input so that the user would use the app without revealing their real locations.
7. The user visits a restaurant and uses the application to scan the restaurant menu to see costs after taxes and tips displayed for each menu item to help them make decisions on which dishes to order.
8. As a person who lives abroad and wish to compare prices. They can specify a specific currency for display so that they can have a similar comparison of what they are used to seeing.

## Technical components

Text recognition: use MLkit text recognition to detect prices, discounts and their keypoints

Augmented Reality display: use ARCore to display actual prices in real time

Communication between AR component and ML: Use ARCore as input for Machine Learning models

## Core features

- Tutorial for using the app

- Welcome Screen :wave: 

  - Display welcome message

  - Buttons: 

    - “Hamburger” menu button

    - Continue

    - Tutorial

  - Logic

    - Loads the last user name

    - Session starts based on location

- Camera View :camera: 

  - Buttons

    - “Menu” hamburger button on the top left corner

    - “Cart” button on the top right corner

    - “Add to Cart” buttons for each price

  - Pop-up View

      - Same buttons as the regular view

      - Display pricing details and breakdown

      - “Add to Cart” button

      - “Cancel” button

  - Display

    - Display prices after calculations

    - Display current total and notify if over budget

    - Display exclamation mark next to prices if the price was more expensive previously

  - Logic

    - Detect multiple grocery store prices/ price tags from camera

    - Detect discount prices and discount logic from camera

    - Detect name of grocery store item from camera

    - Calculate prices after tax for grocery store item

    - Haptic feedback after an item is added to cart

- Cart View :shopping_cart: 

  - Display:

    - Session name

    - Total price

    - Display current list of items, quantity and prices in virtual cart

    - Display :exclamation: mark next to prices if the price was more expensive previously

    - Display spending limit and “$XX.XX over spending limit”

  - Buttons

    - “Back” button to go back to camera view

    - “Menu” hamburger button on the top left corner

    - Option to remove items/change quantity

    - “Complete shopping” to complete session and go back to welcome screen

    - “Edit” button for session name

  - Logic

    - Calculate total price in cart

  - Pop-up View

    - :exclamation: notification for previously lower price

- Settings :gear: 

  - Buttons

    - “Back” button to go back to previous screen

  - Switches

    - Restaurant mode: turn on to display prices for restaurant menus

    - Record/do not record history

    - Haptic feedback

    - Static “Add to Cart” button

    - Override location: use different location instead of current location

    - Override tax rate

  - Set default session spending limit

  - Set tip percentage for restaurants

  - Clear history

  - Pop-up: “Are you sure?”

- Accessibility :wheelchair: 

  - Text to voice for prices

  - Haptic feedback after an item is added to cart

- History :bookmark_tabs: 

  - Buttons

    - “Sort” button on top right corner: by price, by item name, by frequency, by location, clear

    - “Back” on upper left corner

  - Display

    - Display user scanning history by session and location

    - Display price history by item with sorting

    - Text field for searching

  - Logic

    - System tracks user history and it is stored locally

- Nice to have

  - Automatically record scanned items

  - Currency conversion

  - Toggle auto-expand real-price breakdown

  - Item label translation

  - Price comparison for scanned products

  - Accessibility: Option to have a static “Add to Cart” button when there is only one price tag on display

## Wireframes (this is a link to a document in your repo)

See wireframes [here](/dev-docs/HiFi_Wireframes_TruPrice_Team_Avengers.pdf)