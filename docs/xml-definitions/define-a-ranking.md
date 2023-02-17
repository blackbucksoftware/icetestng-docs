---
sidebar_position: 3
---

# Defining Derived Results

This document details how to use Derived Results and how you can define your own Derived Results in IceTest NG.


## Definition

In IceTest NG, a "Derived Result" is any result that is **automatically calculated** from one or more results of the same competition. Derived Results (also being called "Combination Rankings" sometimes) can be used to achieve the following:

* merge results from different tests, for example provide a combined total ranking for two separate T7 classes
* filter results, for example provide a ranking of a V5 class only for members of a certain club
* combine results, for example calculate an overall score for riders who participated in a tölt and a gaited class


## Adding Derived Results to an event

Just like tests, Derived Results can be added either from an official test catalog (provided by FEIF or a national association) or from a custom XML file prepared by the user.

In order to add a Derived Result, go to the **Tests** page and click the competition name in the bread crumb menu on the top of the list to open the Competition Setup popup. 

1. Go to the **Derived Results** tab.
2. The left column shows the available Derived Results.
3. Drag the desired Derived Result to the right column.
4. Close the overlay to save your changes.

See section [XML description](#xml) for details on building your own custom Derived Results in XML.


## Working with Derived Results

Once a Derived Result has been added to the competition, it will be listed on the **Tests** page. Unlike the regular tests, it will feature only a results (flag) icon.

Derived Results are updated automatically. Every time a result is entered for a test that is counting towards a Dervied Result, the calculation will be updated both in IceTestNG and on the ticker website.

If a competition makes use of age classes, Derived Results will feature separate rankings for both all age classes combined and every single age class.


## Defining custom Derived Results <a name="xml"></a>

Users can create their own Derived Results as part of an XML file that can be imported via the **Import Local Tests** page.

The general structure of such a file is as follows:

```jsx title="davos2023.xml"
<?xml version="1.0" encoding="utf-8"?>
<rules xmlns:data="x-schema:idSchema.xml" xmlns:ref="x-schema:refSchema.xml" xmlns="http://feif.org/icetestng">

  <source>LOCAL</source>
  <year>2019</year>
  <revision>1</revision>

  <derived_results>
  	<derived_result>
      <resultcode>CI</resultcode>
      <name>Icelandic Combination</name>
      <description></description>
      <result_type>STA</result_type>
      <blocks>
        <block>
          <name>Tölt</name>
          <required>one</required>
          <marks>1</marks>
          <factor>1</factor>
          <tests>
            <test>
              <testcode>T1</testcode>
              <phase>PREL</phase>
              <factor>1</factor>
            </test>
            <test>
              <testcode>T2</testcode>
              <phase>PREL</phase>
              <factor>1</factor>
            </test>
          </tests>
        </block>
        <block>
          <name>Gaited</name>
          <required>one</required>
          <factor>1</factor>
          <marks>1</marks>
          <tests>
            <test>
              <testcode>F1</testcode>
              <phase>PREL</phase>
              <factor>1</factor>
            </test>
            <test>
              <testcode>V1</testcode>
              <phase>PREL</phase>
              <factor>1</factor>
            </test>
          </tests>
        </block>
      </blocks>
    </derived_result>
  </derived_results>

  <!-- The next tags are used to define custom tests; they are not needed to define Derived Results -->
  <tests></tests>
  <phase_defs></phase_defs>
  <sections></sections>
  <results></results>
  <judges></judges>
  <conversions></conversions>
</rules>
```

The sample XML above shows the definition of the "Icelandic Combination", a ranking that combines a tölt score from either T1 or T2, and the result of a gaited test (F1 or V1).
The file could of course contain definitions for several Derived Results as well as other local competition data like custom tests.

Let's take a look at the different parts:

### Header section

The header section of the XML needs three tags on the root level:

| Tag | Description | Example |
| --- | ----------- | ------- |
| `<source>` |Must be **LOCAL** in user-defined XML files. Required. | _&lt;source&gt;LOCAL&lt;/source&gt;_ | 
| `<year>` |The year of the competition. Required. | _&lt;year&gt;2019&lt;/year&gt;_ | 
| `<revision>` |Revision of the file. In case the file has to be changed/corrected, the revision information needs to be increased by one. Required. | _&lt;revision&gt;1&lt;/revision&gt;_ | 

### &lt;derived\_results&gt; section

The `<derived_results>` section of the file contains one or more definitions. Each definition resides in opening and closing `<derived_result>` tags. 
The following tags are valid inside a `<derived_result>` section:

| Tag | Description | Example |
| --- | ----------- | ------- |
| `<resultcode>` |The short code of the Derived Result, used like a test code (T1, F1, etc.). Maximum length is 8 characters. Required. | _&lt;resultcode&gt;IC&lt;/resultcode&gt;_ | 
| `<name>` |The name of the Derived Result. Maximum length is 100 characters. Required. | _&lt;name&gt;Icelandic Combination&lt;/name&gt;_ |
| `<description>` |A description of the Derived Result. May be empty. Required. | _&lt;description&gt;Tölt score and Gaited score combined.&lt;/description&gt;_ |
| `<result_type>` |**STA** &#124; **TEAM**. Required.<br />STA: Results are calculated per participant.<br />TEAM: Results are calculated per team. | _&lt;result\_type&gt;STA&lt;/result\_type&gt;_ |
| `<required_club>` |Limits the calculation to participants that are members of the club named here. Optional. | _&lt;required\_club&gt;Fákur&lt;/required\_club&gt;_ |


### &lt;blocks&gt; section
Each Derived Result definition consists of at least one `<block>`. A participant or team needs at least one valid result per block to have their total score calculated. These tags are valid inside a `<block>` section:

| Tag | Description | Example |
| --- | ----------- | ------- |
| `<name>` |The name of the block. Maximum length is 20 characters. Required. | _&lt;name&gt;Tölt&lt;/name&gt;_ |
| `<required>` |**ONE** &#124; **ALL** &#124; **ANY**. Required.<br />ONE: Only one result (the best) is needed to qualify for the combination.<br />ALL: Results from all tests in this block are required to qualify.<br />ANY: All results which are available will count, but one result is sufficient. | _&lt;required&gt;ONE&lt;/required&gt;_ | 
| `<marks>` |Number of marks considered in this block. Required. | _&lt;marks&gt;1&lt;/marks&gt;_ |
| `<marks_strict>` |**true** &#124; **false**<br /> If set to true the number of marks specified for the block is exact. if omitted (or false) the number of marks is a maximal value with missing marks counting as “0”. Optional. | _&lt;marks\_strict&gt;1&lt;/marks\_strict&gt;_ |
| `<factor>` |Multiplication factor applied to the block result when calculating the overall derived result. Accepts values between 0.01 and 9.99. Required. | _&lt;factor&gt;1.0&lt;/factor&gt;_ |


### &lt;tests&gt; section
Every block contains at least one -- usually more -- `<test>` node describing a test which belongs to the current event and is meant to contribute to the Derived Result. The following tags are used to describe a `<test>`:

| Tag | Description | Example |
| --- | ----------- | ------- |
| `<testcode>` |The test code whose results should be considered. Maximum length is 8 characters. Required.<br />**%** might be used as wildcard to match more than one test code. | _&lt;testcode&gt;T1&lt;/testcode&gt;_ |
| `<phase>` |**PREL** &#124; **FIN** &#124; **CFIN** &#124; **BFIN** &#124; **AFIN**. Required.<br />The phase of the indicated test code whose results should be considered. | _&lt;phase&gt;PREL&lt;/phase&gt;_ |
| `<factor>` |Multiplication factor applied to the test result when calculating the result of the block. Accepts values between 0.01 and 9.99. Required. | _&lt;factor&gt;1.0&lt;/factor&gt;_ |




Add **Markdown or React** files to `src/pages` to create a **standalone page**:

- `src/pages/index.js` → `localhost:3000/`
- `src/pages/foo.md` → `localhost:3000/foo`
- `src/pages/foo/bar.js` → `localhost:3000/foo/bar`

:::tip My tip

Use this awesome feature option

:::

:::danger Take care

This action is dangerous

:::

:::warning My tip

Use this awesome feature option

:::

:::info Take care

This action is dangerous

:::

## Create your first React Page

Create a file at `src/pages/my-react-page.js`:

```jsx title="src/pages/my-react-page.js"
import React from 'react';
import Layout from '@theme/Layout';

export default function MyReactPage() {
  return (
    <Layout>
      <h1>My React page</h1>
      <p>This is a React page</p>
    </Layout>
  );
}
```

A new page is now available at [http://localhost:3000/my-react-page](http://localhost:3000/my-react-page).

## Create your first Markdown Page

Create a file at `src/pages/my-markdown-page.md`:

```mdx title="src/pages/my-markdown-page.md"
# My Markdown page

This is a Markdown page
```

A new page is now available at [http://localhost:3000/my-markdown-page](http://localhost:3000/my-markdown-page).
