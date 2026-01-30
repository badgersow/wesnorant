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

1. When the number is entered, we know the probability of payment. This probability should be visualized by rendering weshoth item on a terrain, with the probability close to the hit chance. For example, if the probability of payment is 70%, it should be rendered as elven archer in forest. This will visually indicate the expected chance. It's supposed to be funny, because my friends are wesnoth and math nerds.
2. When the item is entered with 100% probability (equal or larger than total), it should be displayed as ulfserker next to the dark adept. It will indicate the chance of 100% kill.

## How to implement this

If something is unclear, ask me questions about the implementation. Then generate the html file and let me test it, I will provide the feedback and we will iterate in this way.