# Shopify Liquid Assignment - Theme Modifications
This repo contains my solution to the Shopify Liquid coding challenge. I worked with the Dawn theme to implement the required features.
<h3>What I did</h3>
I tackled several Liquid templating challenges by modifying the Dawn theme files. The assignment involved creating dynamic elements that respond to product data, user behavior, and time of day.

<h3>Files I modified:</h3>
product-card.liquid
collection.liquid
index.liquid
cart.liquid

<h3>Implementation notes</h3>
<h3>Dynamic Product Badges (product-card.liquid)</h3>
For this task, I added conditional badges that show up based on price and stock levels. Getting the inventory quantity was tricky since I needed to access it through the first variant. I had to convert the price from cents to rupees to make the comparison work correctly.
These badges really pop thanks to some custom CSS I added - went with a bright orange for "Limited Stock" to create urgency and blue for "Budget Pick".
<h3>Custom Collection Filter (collection.liquid)</h3>
The tag filtering was interesting to implement. I went with a simple dropdown approach rather than checkboxes since it's more mobile-friendly. The tricky part was making sure the filter remembered the current selection when the page reloaded.
I spent some time making sure this filter wouldn't break pagination - turns out you need to be careful with how you construct the URLs.
<h3>Time-based Greeting (index.liquid)</h3>
This was straightforward but fun. I had to remember that Liquid's date filter returns a string, so I needed to convert it to a number with the plus: 0 filter before making comparisons.
I tested this by manually changing my computer's time to make sure it switched between greetings correctly. The greeting sits right below the hero image on the homepage.
<h3>Cart Upsell Section (cart.liquid)</h3>
This was the most challenging part. I needed to:
Calculate the cart total
Pull a product from a specific collection based on that total
Make sure I wasn't recommending something already in the cart

I had an issue where the upsell products weren't showing images at first - fixed it by accessing the featured_image property correctly.
Bonus Shipping Message
I added a small progress bar under the shipping message to visually show how close customers are to free shipping. When testing, I found that showing the exact amount needed to reach the threshold was more effective than just a static message.
