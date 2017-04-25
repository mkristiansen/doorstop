# 1.0 Document and Item Creation {#TUT003 }

## 1.1 TUT001 {#TUT001 }

**Creating a New Document and Adding Items**

Enter a VCS working copy:

    $ cd /tmp/doorstop

Create a new document:

    $ doorstop create REQ ./reqs

Add items:

    $ doorstop add REQ
    $ doorstop add REQ
    $ doorstop add REQ

Edit the new items in the default text editor:

    $ doorstop edit REQ1
    $ doorstop edit REQ2

*Parent links:* [REQ003](REQ.html#REQ003), [REQ004](REQ.html#REQ004)

*Child links:* [HLT001](HLT.html#HLT001)

## 1.2 TUT002 {#TUT002 }

**Creating a Child Document with Links to the Parent Document**

Enter a VCS working copy:

    $ cd /tmp/doorstop

Create a new child document:

    $ doorstop create TST ./reqs/tests --parent REQ

Add new items:

    $ doorstop add TST
    $ doorstop add TST

Edit the new items in the default text editor:

    $ doorstop edit TST1
    $ doorstop edit TST2

Add links to item's in the parent document:

    $ doorstop link TST1 REQ1
    $ doorstop link TST1 REQ3
    $ doorstop link TST2 REQ1
    $ doorstop link TST2 REQ2

*Parent links:* [REQ003](REQ.html#REQ003), [REQ004](REQ.html#REQ004), [REQ011](REQ.html#REQ011), [REQ012](REQ.html#REQ012), [REQ013](REQ.html#REQ013)

*Child links:* [HLT001](HLT.html#HLT001)

## 1.3 TUT004 {#TUT004 }

**Removing Items and Links**

Enter a VCS working copy:

    $ cd /tmp/doorstop

Remove a link between two document items:

    $ doorstop unlink TST1 REQ3

Remove a document's item:

    $ doorstop remove REQ3

*Parent links:* [REQ003](REQ.html#REQ003), [REQ011](REQ.html#REQ011), [REQ012](REQ.html#REQ012), [REQ013](REQ.html#REQ013)

*Child links:* [HLT001](HLT.html#HLT001)

## 1.4 TUT008 {#TUT008 }

**Validating the Tree**

Enter a VCS working copy:

    $ cd /tmp/doorstop

Build and validate the tree:

    $ doorstop

*Parent links:* [REQ003](REQ.html#REQ003)

*Child links:* [HLT001](HLT.html#HLT001)

## 1.5 TUT017 {#TUT017 }

### Headings 3

Markdown can be used to format text.

#### Heading 4

##### Heading 5

### Emphasis
Emphasis, aka italics, with *asterisks* or _underscores_.

Strong emphasis, aka bold, with **asterisks** or __underscores__.

Combined emphasis with **asterisks and _underscores_**.

Strikethrough uses two tildes. ~~Scratch this.~~

### Paragraphs
When exporting to html using doorstop newlines
are converted to line breaks.

An empty line is required to start a new paragraph.

### Lists
1. First ordered list item
2. Another item
1. Actual numbers don't matter,
just that it's a numbers

* Unordered list can use asterisks
- Or minuses
+ Or pluses

### Tables
Colons can be used to align columns.

| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |

There must be at least 3 dashes separating each header cell.
The outer pipes (|) are optional, and you don't need to make the
raw Markdown line up prettily. You can also use inline Markdown.

Markdown | Less | Pretty
--- | --- | ---
*Still* | `renders` | **nicely**
1 | 2 | 3

*Parent links:* [REQ004](REQ.html#REQ004)

*Child links:* [HLT001](HLT.html#HLT001)

## 1.6 Sub headings {#TUT018 }

### 1.6.1 TUT019 {#TUT019 }

Sub headings can be created by a level that ends in .0

*Parent links:* [REQ004](REQ.html#REQ004)

*Child links:* [HLT001](HLT.html#HLT001)

# 2.0 Publishing Documents {#TUT005 }

## 2.1 TUT009 {#TUT009 }

**Publishing a Document as Text**

Enter a VCS working copy:

    $ cd /tmp/doorstop

Display the documents on standard output:

    $ doorstop publish req
    $ doorstop publish tst

*Parent links:* [REQ007](REQ.html#REQ007)

*Child links:* [HLT002](HLT.html#HLT002)

## 2.2 TUT010 {#TUT010 }

**Publishing All Documents as an HTML Directory**

Enter VCS working copy:

    $ cd /tmp/doorstop

Create an HTML directory for all documents:

    $ doorstop publish all path/to/htmldir

*Parent links:* [REQ007](REQ.html#REQ007)

*Child links:* [HLT002](HLT.html#HLT002)

# 3.0 Importing Content {#TUT011 }

## 3.1 TUT016 {#TUT016 }

**Importing a File**

Enter a VCS working copy:

    cd /tmp/doorstop

Create a document for the import:

    doorstop create HLR

Import from an exported document:

    doorstop import path/to/exported.xlsx HLR

*Parent links:* [REQ016](REQ.html#REQ016)

*Child links:* [HLT003](HLT.html#HLT003)

## 3.2 TUT012 {#TUT012 }

**Importing a Document**

Enter a VCS working copy:

    $ cd /tmp/doorstop

Import a document:

    $ doorstop import --document HLR reqs/hlr

Import a document with a parent:

    $ doorstop import --document LLR reqs/llr --parent HLR

*Parent links:* [REQ016](REQ.html#REQ016)

*Child links:* [HLT003](HLT.html#HLT003)

## 3.3 TUT013 {#TUT013 }

**Importing an Item**

Enter a VCS working copy:

    $ cd /tmp/doorstop

Import an item:

    $ doorstop import --item HLR HLR001

Import an item with attributes:

    $ doorstop import --item LLR LLR001 --attr "{'text': 'The item text.'}"

*Parent links:* [REQ016](REQ.html#REQ016)

*Child links:* [HLT003](HLT.html#HLT003)

# 4.0 Exporting Content {#TUT014 }

## 4.1 TUT015 {#TUT015 }

**Exporting a Document**

Enter a VCS working copy:

    $ cd /tmp/doorstop

Export a document to standard outout:

    $ doorstop export LLR

Export all documents to a directory:

    $ doorstop export all dirpath/to/exports

Export documents using specific formats:

    $ doorstop export REQ path/to/req.xlsx

*Parent links:* [REQ017](REQ.html#REQ017)

*Child links:* [HLT004](HLT.html#HLT004)
