So here's the snippet works

You activate the JS one use: 

`<span class="price" data-base-price="$16.97">$16.97</span>`


Where data-base-price="$16.97"   is the price that will be changed for currencies, while $16.97 is the default price. It'll automatically be replaced with the corresponding price for each location if both values are the same.

This whole snippet is built off of USD prices, modifying it will mean changing most of the values.

The JS and the PHP plugin don't just exchange the price from USD to the person's current location but also reduce/add a percentage to match the country's standards. 

e.g. In Bulgaria, books are 14-22 BGN, but if you just convert 16.97 USD into BGN it'll be 33 BGN which is EXPENSIVE for the income of people there, so it'll also multiply 33 * 0.60 = 18 BGN thus maching the countries standard.

The function that achieves this is `stndardRate` located in the `countryData` array.

It'll also make sure to convert sums larger than 100,000 to instead make them $100k thus matching the style you'd most likely use.

For any text, you'll want to use the above HTML <span> piece to display the correct prices. You can straight up use the JS as it is.

For the checkout, you'll want to modify the PHP plugin to match your site.

To be able to access the location of the reader you'll also need to add the snippet for accessing the location. It's only used for the JS as the PHP has it's own version of it.

















