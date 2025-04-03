# Overall Rankings

This document details how to use Derived Results aka Overall Rankings and how you can use pre-made ones or define your own in IceTest-NG.


## What is a Derived Result?

In IceTest-NG, a "Derived Result" is any result that is **automatically calculated** from one or more results of the same competition. Derived Results (sometimes also referred to as "Overall Ranking" or "Combination Ranking") can be used to achieve the following:

* Merge results from different tests, for example provide a combined total ranking for two separate T7 classes
* Filter results, for example provide a ranking of a V5 class only for members of a certain club
* Combine results, for example calculate an overall score for riders who participated in a tölt and a gaited class


## Adding Derived Results to an event

Just like tests, Derived Results can be added either from an official test catalog (provided by FEIF or a national association) or from a custom XML file prepared by the user.

In order to add a Derived Result, go to the **Tests** page and click the competition name in the bread crumb menu on the top of the list to open the Competition Setup popup. 

1. Go to the **Derived Results** tab.
2. The left column shows the available Derived Results.
3. Drag the desired Derived Result to the right column.
4. Close the overlay to save your changes.

See section [XML Definitions](custom-rankings-xml.md) for details on building your own custom Derived Results in XML.


## Working with Derived Results

Once a Derived Result has been added to the competition, it will be listed on the **Tests** page. Unlike the regular tests, it will feature only a results (flag) icon.

Derived Results are updated automatically. Every time a result is entered for a test that is counting towards a Dervied Result, the calculation will be updated both in IceTestNG and on the ticker website.

If a competition makes use of age classes, Derived Results will feature separate rankings for both all age classes combined and every single age class.




