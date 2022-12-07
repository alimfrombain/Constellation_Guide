# Constellation User Guide

## Overview

This guide walks through the latest key use cases for Constellation. In particular, the guide demonstrates how to perform updates to item tags in a few different ways.

## Tagging Use Cases

### Individual Tag Update

To update a specific item's tag follow the instructions here:

1. Within _Sources_, select "Tagging Output" and "Fetch Product Input" and click Update
2. Within _Query_, under Item Filter Selection select "PRODUCT_DESCRIPTION" under the first dropdown and then "contains" for the second dropdown. Leave the third dropdown as "value". Then in the fourth dropdown, input the item's description or a subset of it so that the item appears in the output.
3. Under _Characteristic View Selection_, add Selects for each field you will need in the output. Choose each field in the first dropdown for each Select, leaving the second dropdown as "itemLevel". You will at least need a Select for "PRODUCT_DESCRIPTION" and the taxonomy you would like to update such as "Google Taxonomy" or "Pyxis Taxonomy". Click the Update button in the bottom right corner to confirm changes.
4. You may now load the data by clicking the red, circular refresh button. This may take a few minutes so do not hit refresh until the results appears.
5. In the output identify the row containing the item in question. Click on the text for the taxonomy column to update that item's tag. The data will now update and may take a few moments.

![Individual Update](Individual_Update.png)

### Identify and Correct Multiple Items Tagged to the Wrong Category

To update multiple incorrectly tagged items to a certain tag see the example here:

Let's say we want to make sure all Skirt items from a set of merchants are tagged as such. To do this, we can query all items containing "Skirt" in their product description and check the taxonomy field to see whether any are misclassified. We can then bulk update the misclassified items.

1. Within _Sources_, select "Tagging Output" and "Fetch Product Input" and click Update
2. Within _Query_, under _Item Filter Selection_ select "PRODUCT_DESCRIPTION" under the first dropdown and then "contains" for the second dropdown. Leave the third dropdown as "value". Then in the fourth dropdown, input "skirt".
3. Then, still under _Item Filter Selection_, click "+Rule" and select "PRODUCT_DESCRIPTION" under the first dropdown and then "is not null" for the second dropdown.
4. We now input the set of merchants we are concerned with. Still within _Item Filter Selection_, click "+Group" and switch the first dropdown from "AND" to "OR". Next click "+Rule" until we have enough rules for each merchant. The merchants we are concerned about are "Shein", "Adidas", and "Uniqlo" so we will click "+Rule" 3 times. 
5. For each of the 3 new rules, we will select "Brand" for the first option, "contains" for the second, leave the thrid as "value", and input a string identfying the merchant without over-filtering rows.
6. Under _Characteristic View Selection_, add Selects for each field you will need in the output. Choose each field in the first dropdown for each Select, leaving the second dropdown as "itemLevel". You will at least need a Select for "PRODUCT_DESCRIPTION" and the taxonomy you would like to update such as "Google Taxonomy" or "Pyxis Taxonomy". It may also be helpful to include "Brand". Click the Update button in the bottom right corner to confirm changes.
7. You may now load the data by clicking the red, circular refresh button. This may take a few minutes so do not hit refresh until the results appears.
8. Once the data loads, we can then filter the taxonomy column to find Skirt items that are not tagged as such. Selected the "FILTERS" button above the output table and select the taxonomy field in the output table (e.g. "Google Taxonomy") for the first dropdown. In the second dropdown (Operator), select "not contains" and in the thrid dropdown (Value) input "skirt".
9. Now refresh the table by clicking the red, circular refresh button. This may take a few moments. 
10. The output will now show Skirt items that are not tagged as Skirts. We can update these items by first selecting all items by checking the square in the first column of the header row of the table. Then clicking the "Update all" button. In the first dropdown of the pop-up select the taxonomy column (e.g., "Google Taxonomy") and in the second select the appropriate tag to update the items to. Then, click "Update".

### Importing / Exporting Rules

\[Placeholder]

## Troubleshooting and Contact

For assistance in using Constellation, please reach out to the Pyxis Constellation team.
