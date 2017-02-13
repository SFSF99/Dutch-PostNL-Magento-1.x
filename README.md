# Dutch-PostNL-Magento-1.x

Dutch PostNL (Parcelware) manual rates packages and letters national and international with letter logic, letterbox post (brievenbus pakje post)

(questions at <a href="https://community.magento.com/t5/Off-Topic/Topic-for-questions-about-my-free-Magento-1-x-and-2-x-extensions/m-p/60205#U60205">Magento Forum</a>)

(more info about this module in <a href="https://www.ooawebstore.eu">webstore</a>)

PostNL has an own free module the last years. So you may use this extension as an shipment module or as a code example to learn from. 

Recently tested in 1.8 and 1.9!

Extension since 2011 successfully used in many Dutch webshops and had been maintained as soon as shipping policy changed at PostNL. Also included letterbox package ( brievenbuspakje ) since 2014.

The interface with Parcelware - desktop/web have been included in this module (extension). Such an interface is only an excel sheet with shipping data which can be imported in Parcelware/Parcelweb. These days there is no feedback anymore via an excel sheet to the webshop (from Parcelware/Parcelweb). But with a own made program at Ooawebstore.eu, it is still possible to import track&trace codes automatically in the webshop (not free). The download of orders for Parcelware can be removed by switching off the module OOA_Orders. The status for these orders can be set in the shipment module.

If you want to couple a COD payment method to the COD shipment method you need to set this method code in Methods.php (see inside extension).

During installation of the extension 5 attributes have been added, you will see this attributes when maintaining products in the admin. Only added to the default attribute set.

These are all possibilities for Dutch TNTpost (PostNL) single post. Weights must here be filled in grams, heights in cm (for letters) and rates in Euro (all in 2 decimals). On the product pages you may fill in if a product must be send as letter or package, the product may be send with PostNL, and a seal bag must be used (at some options always included). And of course the height of a product, if this product can be send as a letter.

By request of a customer a choice has added how to calculate what fits in 1 envelope. The choices are with the height of a product (all products are mounted up in the letter, always correct) OR with the maximum quantity of a product what fits in a letter (take that spacious). In this last case it will be calculated as follows (sometimes the rate will be calculated too low if it does not fit) : e.g. product A max. 9, product B max. 3, product C max. 6, than 3xA + 1xB + 2xC would be possible qua volume (1/3 + 1/3 + 1/3 = 1) etc.

Rates must be entered as follows (max. weight):(rate),(max. weight)(rate),etc. Use for rates a decimal point (so no comma).

Take care: don't add the Netherlands to the countries below, the Netherlands is the country for which the national rates apply.

Multiple packages are also possible but not for speed service (higher the maximum weight is not healthy for your back). Multiple packages have all of course the same rate class.

All text can be changed in the language .csv files (Dutch or English).

The logic of this module is as follows:

- if at least one product on the shopping cart is 'no PostNL' the rates are not displayed

- if the maximum box weight is set to lower 10000 grams, the rates are not displayed (calculated rates not efficient in that case)

- if at least one product on the shopping cart is a 'package' the whole shipment is a 'package'

- if the whole shipment is a 'letter' and the weight is greater than the maximum weight of a normal letter, the whole shipment is a 'package'

- if the whole shipment is a 'letter' and the height is greater than the maximum height of a normal letter, the whole shipment is a 'package'

- if not one 'letter' shipment is enabled, the whole shipment is a 'package' in case it is a 'letter' shipment

- a rate class option is not displayed if the weight is greater than the maximum weight for that rate class option AND no multiple boxes are allowed/enabled for that option

- if a COD option is chosen, only the payment modules 'COD' are displayed (if installed, otherwise all; e.g. Cash On Delivery is a COD module)

So what do you need to do for this extension:
- download .zip file and unpack
- copy contents to your Magento root directory (where you see directory /app)
- clear cache (and mostly logoff and login admin again) and reindex

Extension support:

No support (too busy), but a few questions will be answered in the Magento forum (see link above).

Questions will be NEVER answered per email!
