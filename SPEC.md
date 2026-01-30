# Wesnorant specification

I want to create a single HTML file with a Javascript web application. It will be called "Wesnorant".

## Functional requirements

The idea is described here: https://messymatters.com/expectorant/. I want this application to be used by a person sitting at the restaurant and looking at the bill. The user will enter the total bill amount to start the session. The user then enters individual items one by one. On each item, the algorithm will run and calculate whether this item triggers the payment. If yet, it will be displayed, and the session will end. If not, the user will be asked for the next item. This continues until there is the last item on the bill. It will be paid by the person who entered it.

I want the design to be simple. If there are multiple items with the same price, the user should enter them one by one. The app shouldn't care about who ordered what, the user will keep it in their head. Once the session has started, the total amount will automatically be kept updated, it can't be changed manually. At any time the session can be restarted.

When the user enters the sum, there should be a separate button to "confirm". The application must be very visual, it should be obvious when the "payment" triggers, and which sum triggered it.

In the edge case where item is more expensive than the total, should be handled gracefully. Somewhere there was a mistake, but it doesn't matter. It means it's the last person and they should pay.

## Technical preferences

I want to have a single html file with all the Javascript code inside it. It will be always used from phone, never from desktop. Prioritize large font, ease of entry from the mobile device.

I want to use minimal dependencies. The overall design should be brutalist and minimalistic. I only intend this application to be used by myself and my friends.

I will host it at my personal website at https://kocour.dev/wesnorant.html

## Visual design

I want the design to follow Wesnoth video game. It's a open source game and all assets are free. The "wesnoth" theme will work in two different aspects.

1. When the number is entered, we know the probability of payment. This probability should be visualized by rendering weshoth item on a terrain, with the probability close to the hit chance. For example, if the probability of hitting a unit is 30%, it should be rendered as saurian in the swamp (who has defense 70% and chance to be hit 30%). This will visually indicate the expected chance. It's supposed to be funny, because my friends are wesnoth and math nerds.
2. When the item is entered with 100% probability (equal or larger than total), it should be displayed as ulfserker next to the dark adept (with no background). It will indicate the chance of 100% kill.

Background terrains must always look like hexes. Images and text should never overlap.
On 100% probability, ulfserker and dark adept should be displayed next to each other without backgrounds.
On game over, a ghoul should be displayed without background.
The app favicon should be ghoul icon.

The following units should be used to display probability:

- low probability: merman in the water
- medium: spearman in plains
- high probability: mage on a plain
- 100% probability: ulfserker next to a dark adept

## Example flow

The application starts with the prompt for the total bill amount.

The user enters 10 and clicks "Start".

The application displays: "Remaining: 10". Enter item price.

The user enters 3 in the window. It's close to elf probability (30%).
When the number is entered, the elf in the forest appears (this is still before the confirmation).
The user clicks on "Enter" or "Confirm", the RNG runs and determines no payment.
The elf dissapears and "next item" appears. The total sum is decreased to 7.

The user enters "4". The probability is close to the human in the field. It is displayed.
RNG runs, and this times the user pays.
It displays the icon of a ghoul, and says "Item with price 4 pays". Only the restart button is available.

## How to implement this

If something is unclear, ask me questions about the implementation. Then generate the html file and let me test it, I will provide the feedback and we will iterate in this way.