---
sidebar_position: 2
---

# Test Examples

This page features **real-world examples** of custom tests used by organizers in various countries.
You can examine the XML used for test definition, and even download the complete XML file to modify it or import it into your own IceTestNG competition.


:::tip Test your tests

It's recommended to try out custom test definitions on the demo system first before importing them into a real event.

:::


## Fivegait on Ice

This test is used by competitions on ice. It uses only tölt, trot, and pace as sections. At the same time, the number of finalists is increased to 7. There is no choice of rein, and the default group size for the PREL round is 4.

```jsx title="davos2023.xml"
<tests>
  <data:test id="XF1">
    <testCode>XF1</testCode>
    <testName>Eisfünfgangpreis spezial</testName>
    <finalists>7</finalists>
    <phases>
      <phase>
        <name>PREL</name>
        <ref:phase_def ref="FOUR_RIDER_PREL" />
      </phase>
      <phase>
        <name>BFIN</name>
        <ref:phase_def ref="XF1" />
      </phase>
      <phase>
        <name>AFIN</name>
        <ref:phase_def ref="XF1" />
      </phase>
      <phase>
        <name>SECR</name>
        <ref:phase_def ref="XF1" />
      </phase>
    </phases>
  </data:test>
</tests>

<phase_defs>
  <data:phase_def id="XF1">
    <reinChoice>false</reinChoice>
    <groupSize>4</groupSize>
    <dropSections/>
    <ref:result ref="normal"/>
    <sections>
      <section>
            <name>Tölt</name>
            <description>Tölt</description>
            <factor>1.0</factor>
            <canDrop>false</canDrop>
          </section>
          <section>
            <name>Trab</name>
            <description>Trab</description>
            <factor>1.0</factor>
            <canDrop>false</canDrop>
          </section>
          <section>
            <name>Rennpass</name>
            <description>Rennpass</description>
            <factor>1.0</factor>
            <canDrop>false</canDrop>
          </section>
    </sections>
    <judges>
      <ref:judge ref="oval" />
      <ref:judge ref="oval" />
      <ref:judge ref="oval" />
      <ref:judge ref="oval" />
      <ref:judge ref="oval" />
    </judges>
  </data:phase_def>

  <data:phase_def id="FOUR_RIDER_PREL">
      <reinChoice>false</reinChoice>
      <groupSize>4</groupSize>
      <dropSections/>
      <ref:result ref="normal"/>
      <sections>
        <ref:section ref="preliminary"/>
      </sections>
      <judges>
        <ref:judge ref="ovalPreliminary" />
        <ref:judge ref="ovalPreliminary" />
        <ref:judge ref="ovalPreliminary" />
        <ref:judge ref="ovalPreliminary" />
        <ref:judge ref="ovalPreliminary" />
      </judges>
    </data:phase_def>
</phase_defs>
```
You can download the full XML file here: [davos2023.xml](/xml/davos2023.xml).

## Fourgait on Ice

Similiar to Fivegait on Ice, this test definition is limited to slow tölt, trot, and medium to fast speed tölt. There are 7 finalists, no choice of rein, and the default group size for the PREL round is 4.

```jsx title="davos2023.xml"
<tests>
  <data:test id="XV1">
    <testCode>XV1</testCode>
    <testName>Eisviergangpreis spezial</testName>
    <comments />
    <qualification>Extra</qualification>
    <worldRanking>false</worldRanking>
    <heats>none</heats>
    <finalists>7</finalists>
    <phases>
      <phase>
        <name>PREL</name>
        <ref:phase_def ref="FOUR_RIDER_PREL" />
      </phase>
      <phase>
        <name>BFIN</name>
        <ref:phase_def ref="XV1" />
      </phase>
      <phase>
        <name>AFIN</name>
        <ref:phase_def ref="XV1" />
      </phase>
      <phase>
        <name>SECR</name>
        <ref:phase_def ref="XV1" />
      </phase>
    </phases>
  </data:test>
</tests>

<phase_defs>
  <data:phase_def id="XV1">
    <reinChoice>false</reinChoice>
    <groupSize>4</groupSize>
    <dropSections/>
    <ref:result ref="normal"/>
    <sections>
      <section>
            <name>Langsamer Tölt</name>
            <description>Langsamer Tölt</description>
            <factor>1.0</factor>
            <canDrop>false</canDrop>
          </section>
          <section>
            <name>Trab</name>
            <description>Trab</description>
            <factor>1.0</factor>
            <canDrop>false</canDrop>
          </section>
          <section>
            <name>Mittlerer bis schneller Tölt</name>
            <description>Mittlerer bis schneller Tölt</description>
            <factor>1.0</factor>
            <canDrop>false</canDrop>
          </section>
    </sections>
    <judges>
      <ref:judge ref="oval" />
      <ref:judge ref="oval" />
      <ref:judge ref="oval" />
      <ref:judge ref="oval" />
      <ref:judge ref="oval" />
    </judges>
  </data:phase_def>
  

  <data:phase_def id="FOUR_RIDER_PREL">
      <reinChoice>false</reinChoice>
      <groupSize>4</groupSize>
      <dropSections/>
      <ref:result ref="normal"/>
      <sections>
        <ref:section ref="preliminary"/>
      </sections>
      <judges>
        <ref:judge ref="ovalPreliminary" />
        <ref:judge ref="ovalPreliminary" />
        <ref:judge ref="ovalPreliminary" />
        <ref:judge ref="ovalPreliminary" />
        <ref:judge ref="ovalPreliminary" />
      </judges>
    </data:phase_def>
</phase_defs>
```
You can download the full XML file here: [davos2023.xml](/xml/davos2023.xml).

