---
sidebar_position: 4
---

# Custom Derived Results: Examples

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

```jsx title="roderath2022.xml"
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

You can download the full XML file here: [roderath2022.xml](/xml/roderath2022.xml).

A new page is now available at [http://localhost:3000/my-react-page](http://localhost:3000/my-react-page).

## Create your first Markdown Page

Create a file at `src/pages/my-markdown-page.md`:

```mdx title="src/pages/my-markdown-page.md"
# My Markdown page

This is a Markdown page
```

A new page is now available at [http://localhost:3000/my-markdown-page](http://localhost:3000/my-markdown-page).
