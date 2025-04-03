# Importing Data from Sporti

This document describes how you can import participants' data collected with [Sporti](https://www.sporti.dk/) into IceTestNG.


## Requirements

The following data need to exist in IceTestNG before importing a Sporti file:

* the competition itself
* [the tests available](#defineTest)
* [the age classes](#age)


## How to import data

Sporti files can be imported by opening the Setup - [Competitions](competitionList.cfm) page and selecting the competition you want to import the Sporti data into:

1. Go to the **Import Data** tab.
2. Select the Sporti file from your computer. [See how to generate it properly](#exportFile)
3. Set the column delimiter to **tab**.
4. Adjust the further import settings if needed.
5. Click the **Import Data** button to start the import




## Recognized column titels

IceTestNG will recognize these column titels in the import file:


| Column in CSV     | Entity in NG | Column in NG  | Example |
| -------------- |:-------------:| -----|---|
| `STA`      | participant | start number | _1_ |
| **`FEIFID`**   | horse       |   FEIF-ID | _NO2010108055_ |
| **`name_horse`** | horse     |   name of horse | _Þokki frá Árgerði_ |
| **`rider`**         | person      |    full name | _Jane Doe_ |
| `birthday_horse`| horse      |    date of birth | _2010-7-20_ |
| `owner`| horse      |    horse owner | _Jane Doe_ |
| `breeder`| horse      |    horse breeder | _John Doe_ |
| `color`| horse      |    color | _Chestnut_ |
| `marking`| horse      |    marking | _Star_ |
| `country_horse`| horse      |    country of origin | _NO_ |
| `f`| horse      |    sire | _Þokki frá Bjarnanesi_ |
| `ff`| horse      |    father's father | _Stormur frá Bjarnanesi_ |
| `fm`| horse      |    father's mother | _Gláma frá Eyjarhólum_ |
| `m`| horse      |    dam | _Nös frá Árgerði_ |
| `mf`| horse      |    mother's father | _Feykir frá Hafsteinsstöðum_ |
| `mm`| horse      |    mother's mother | _Irpa frá Árgerði_ |
| `sex_horse`| horse      |    gender | _Stallion_ |
| `microchip`| horse      |    microchip | _352206000045XXX_ |
| `name_first`   | person      |    first name | _Jane_ |
| `name_last`    | person      |    last name | _Doe_ |
| `birthday`     | person      |    date of birth | _1986-6-23_ |
| `city`         | person      |    city | _Vienna_ | 
| `mobile`       | person      |    mobile | _+1234567890_ | 
| `phonemobile`  | person      |    mobile | _+1234567890_ | 
| `email`       | person      |    email | _hello@gmail.com_ | 
| `team`         | participant      |    team | _Tölty Tölters_ |
| `club`         | participant      |    club | _Katla_ | 
| `class`         | participant      |    age class | _Senior_ |
| `stable`         | participant      |    stabling option | _Box_ |


Column titles not mentioned in the table above will be treated as test codes. 

Only the **bold columns** are required, all others are optional.


## Post import operations

IceTestNG will try to match all FEIF-IDs against [WorldFengur](http://www.worldfengur.com) after import. 
If the FEIF-ID is known to WorldFengur, the horse data will be used in IceTestNG as well.
The matching process can take some time and happens automatically in the background.

## Export from Sporti <a name="exportFile"></a>
When exporting the file from Sporti, make sure the settings are as seen below:
![](./docs/images/sporti.jpg)

You need to convert the resulting xls-file to a UTF-8 comma separated file by opening it in Excel and pressing Save as or Export.

## Defining the tests properly<a ame="defineTest"></a>
You need to make sure that the test columns in the CSV match the test codes in IceTestNG:
![](./docs/images/testlist.jpg)


If you have multiple instances of a test, e.g. T8.s and T8.j, you can edit the testcode by pressing the pen icon. When a test has been assigned a new testcode, it will reappear in the list, and you can drag it into your event again.

## Defining age classes <a name="age"></a>
If you want IceTestNG to assign age classes, you need to define them for your event first:
![](./docs/images/ageclass.jpg)

And set the switch to on in the import settings:
![](./docs/images/ageswitch.jpg)

## If you get an error
If IceTestNG reports that it could not recognise column or test name, first make sure you defined the test properly. If the column is safe to skip, you can try to copy the columns names suggestion into the field "Skip columns in file”


