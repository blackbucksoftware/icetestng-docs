# XML Definitions

Users can create their own Derived Results as part of an XML file that can be imported via the **Import Local Tests** page.

The general structure of such a file is as follows:

```xml
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
| `<testcode>` |The test code whose results should be considered. Maximum length is 8 characters. Required. **%** might be used as wildcard to match more than one test code. | _&lt;testcode&gt;T1&lt;/testcode&gt;_ |
| `<phase>` |**PREL** &#124; **FIN** &#124; **CFIN** &#124; **BFIN** &#124; **AFIN**. Required. The phase of the indicated test code whose results should be considered. | _&lt;phase&gt;PREL&lt;/phase&gt;_ |
| `<factor>` |Multiplication factor applied to the test result when calculating the result of the block. Accepts values between 0.01 and 9.99. Required. | _&lt;factor&gt;1.0&lt;/factor&gt;_ |



