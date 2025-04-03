# Custom Derived Results: Examples


## Kreismeister aka County Champion
Let's start with a ranking that uses results from three blocks (tölt, gaited tests, and a third block featuring dressage, trail, and pace disciplines). It's being used at a club championship event in Roderath (Germany). Side note: This event takes place at the exact venue where the very first European Championships were held.

While all blocks are counting equally, the tests within each block have different factors, for example T1 results are multiplied by 0.85, while T7 scores are only multiplied by 0.4.

Riders must ride at least one test from each block, and the best result from each block is used to calculate the final score. 

```xml
<!--
  Note: This is only an excerpt, not the full file.
  You can download the complete file below.
!-->
<derived_result>
  <resultcode>KR.1</resultcode>
  <name>Kreismeister</name>
  <description></description>
  <result_type>STA</result_type>
  <blocks>
    <block>
      <name>Tölt</name>
      <required>one</required>
      <factor>1</factor>
      <marks>1</marks>
      <tests>
        <test>
          <testcode>%.T1</testcode>
          <phase>PREL</phase>
          <factor>0.85</factor>
        </test>
        <test>
          <testcode>%.T2</testcode>
          <phase>PREL</phase>
          <factor>0.85</factor>
        </test>
        <test>
          <testcode>%.T4</testcode>
          <phase>PREL</phase>
          <factor>0.8</factor>
        </test>
        <test>
          <testcode>%.T3</testcode>
          <phase>PREL</phase>
          <factor>0.8</factor>
        </test>
        <test>
          <testcode>%.T5</testcode>
          <phase>PREL</phase>
          <factor>0.6</factor>
        </test>
        <test>
          <testcode>%.T6</testcode>
          <phase>PREL</phase>
          <factor>0.6</factor>
        </test>
        <test>
          <testcode>%.T7</testcode>
          <phase>PREL</phase>
          <factor>0.4</factor>
        </test>
      </tests>
    </block>
    <block>
      <name>Gang</name>
      <required>one</required>
      <factor>1</factor>
      <marks>1</marks>
      <tests>
        <test>
          <testcode>%.V1</testcode>
          <phase>PREL</phase>
          <factor>0.85</factor>
        </test>
        <test>
          <testcode>%.F1</testcode>
          <phase>PREL</phase>
          <factor>0.85</factor>
        </test>
        <test>
          <testcode>%.V2</testcode>
          <phase>PREL</phase>
          <factor>0.8</factor>
        </test>
        <test>
          <testcode>%.F2</testcode>
          <phase>PREL</phase>
          <factor>0.8</factor>
        </test>
        <test>
          <testcode>%.V3</testcode>
          <phase>PREL</phase>
          <factor>0.6</factor>
        </test>
        <test>
          <testcode>%.V5</testcode>
          <phase>PREL</phase>
          <factor>0.4</factor>
        </test>
      </tests>
    </block>
    <block>
      <name>Nebenplatz</name>
      <required>one</required>
      <factor>1</factor>
      <marks>1</marks>
      <tests>
        <test>
          <testcode>%.D3</testcode>
          <phase>FIN</phase>
          <factor>0.8</factor>
        </test>
        <test>
          <testcode>%.D4</testcode>
          <phase>FIN</phase>
          <factor>0.7</factor>
        </test>
        <test>
          <testcode>%.D5</testcode>
          <phase>FIN</phase>
          <factor>0.6</factor>
        </test>
        <test>
          <testcode>%.D6</testcode>
          <phase>FIN</phase>
          <factor>0.4</factor>
        </test>
        <test>
          <testcode>%.TR1</testcode>
          <phase>FIN</phase>
          <factor>0.4</factor>
        </test>
        <test>
          <testcode>%.PP1</testcode>
          <phase>FIN</phase>
          <factor>0.8</factor>
        </test>
        <test>
          <testcode>%.P2</testcode>
          <phase>FIN</phase>
          <factor>0.7</factor>
        </test>
      </tests>
    </block>
  </blocks>
</derived_result>
```

You can download the full XML file here: [roderath2022.xml](xml/roderath2022.xml).


## One Ranking for All

This example is very similar to the first one: It has three blocks of tests and riders are required to take part in each block to get ranked. 

However, there is one difference: Some tests are listed more than once, for example T8 shows up as K.M.T8 and %.C.T8. This is done to allow for the tests to have different factors: K.M.T8 is multiplied by 1, while %.C.T8 is multiplied by 0.7. The reason? K.M.T8 is a childrens' class test, while %.C.T8 is a test for adults. The organizer decided to have everybody in one ranking, but wanted to boost the scores of the children a bit to make it more fair.

```xml
<!--
  Note: This is only an excerpt, not the full file.
  You can download the complete file below.
!-->
<derived_result>
      <resultcode>TS</resultcode>
      <name>Turniersiegerwertung</name>
      <description></description>
      <result_type>STA</result_type>
      <blocks>
        <block>
          <name>Gruppe 1</name>
          <required>one</required>
          <marks>1</marks>
          <factor>1</factor>
          <tests>
            <test>
              <testcode>K.M.T8</testcode>
              <phase>PREL</phase>
              <factor>1</factor>
            </test>
            <test>
              <testcode>K.L.T7</testcode>
              <phase>PREL</phase>
              <factor>1</factor>
            </test>
            <test>
              <testcode>%C.T8</testcode>
              <phase>PREL</phase>
              <factor>0.7</factor>
            </test>
            <test>
              <testcode>%A.T7</testcode>
              <phase>PREL</phase>
              <factor>0.7</factor>
            </test>
            <test>
              <testcode>%.T6</testcode>
              <phase>PREL</phase>
              <factor>1</factor>
            </test>
            <test>
              <testcode>%.T3</testcode>
              <phase>PREL</phase>
              <factor>1</factor>
            </test>
            <test>
              <testcode>%.T4</testcode>
              <phase>PREL</phase>
              <factor>1</factor>
            </test>
          </tests>
        </block>
        <block>
          <name>Gruppe 2</name>
          <required>one</required>
          <factor>1</factor>
          <marks>1</marks>
          <tests>
            <test>
              <testcode>K.M.V6</testcode>
              <phase>PREL</phase>
              <factor>1</factor>
            </test>
            <test>
              <testcode>K.L.V5</testcode>
              <phase>PREL</phase>
              <factor>1</factor>
            </test>
            <test>
              <testcode>%C.V5</testcode>
              <phase>PREL</phase>
              <factor>0.7</factor>
            </test>
            <test>
              <testcode>%E.V5</testcode>
              <phase>PREL</phase>
              <factor>0.7</factor>
            </test>
            <test>
              <testcode>%.V3</testcode>
              <phase>PREL</phase>
              <factor>1</factor>
            </test>
            <test>
              <testcode>%.V2</testcode>
              <phase>PREL</phase>
              <factor>1</factor>
            </test>
            <test>
              <testcode>%.F2</testcode>
              <phase>PREL</phase>
              <factor>1</factor>
            </test>
          </tests>
        </block>
        <block>
          <name>Gruppe 3</name>
          <required>one</required>
          <factor>1</factor>
          <marks>1</marks>
          <tests>
            <test>
              <testcode>K.M.D8</testcode>
              <phase>FIN</phase>
              <factor>1</factor>
            </test>
            <test>
              <testcode>%.D6</testcode>
              <phase>FIN</phase>
              <factor>1</factor>
            </test>
            <test>
              <testcode>%.TR1</testcode>
              <phase>FIN</phase>
              <factor>1</factor>
            </test>
            <test>
              <testcode>%.D4</testcode>
              <phase>FIN</phase>
              <factor>1</factor>
            </test>
          </tests>
        </block>
      </blocks>
    </derived_result>
```

You can download the full XML file here: [meppen2023.xml](xml/meppen2023.xml).
