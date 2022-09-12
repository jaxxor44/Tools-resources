---
banner: "https://images.unsplash.com/photo-1547394765-185e1e68f34e?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2070&q=80"
banner_y: 0.6
banner_lock: true
cards-deck: test
---
# Meta guidelines
- Use conceptual note taking.
- link to other notes _as you write them_.
	- a single link is worth more than a sentence.
- For each unit in a course, create a new folder, it just looks nicer and takes up less YAML space.
- When able, connect to the closest entity before reaching to other units or classes.
- Each Class should have a:
	- `_Overview_` note
	- `_Attachments_` folder
		- Be sure to point the attachments setting to the new folder.
- Create a tasks collection in overview, specific to that class/section
- Create Tasks as needed wherever they arrive in the note.
	- See the `Tasks` community extension.
- Each Class is its own GitHub repository.
	- Does this allow the Tools & resources folder to be included in each release?
	1. Class notes need backup (because done or otherwise)
	2. Create `README` file inside the class named folder, `C838 - foo bar/README.md`
	3. Open GitHub Desktop and click `Add Existing Repository`.
		1. This will force GitHub Desktop to include files in that folder automatically.
	4. Navigate to the course name folder `C:/foo/bar/C838 - Foo bar`
	5. Take GitHub's suggestion and create a new repository there.
	6. Add a description.
	7. Click `Publish Repo` and make it public.
	8. Go to GitHub and feed the link back into the readme
	9. Send the Link to your Mentor.

# Advanced tables
- https://github.com/tgrosinger/advanced-tables-obsidian
>To create a table, create a single `|` character, then type the table's first heading and press Tab. Continue entering headings and pressing Tab until all the headings are created. Press Enter to go to the first row. Continue filling cells as before, and press Enter again for each new row.

| Hotkey             | Action        |
| ------------------ | ------------- |
| *tab*              | Next Cell     |
| *Shift*+*Tab*      | Previous Cell |
| *Enter*            | Next Row      |
| *Ctrl*+*Shift*+*D* | Open table controls slidebar              |
## multiple entries in one cell
| Week | Lesson                                          |
| ---- | ----------------------------------------------- |
| 1    | - Unit 1 - Welcome <br /> - Unit 2 -Intro to IT |
the secret is ```<br />```

# Callouts
> [!INFO] > Here's a callout block. 
> > It supports **markdown** and [[Internal link|wikilinks]].
> > https://help.obsidian.md/How+to/Use+callouts

> [!FAQ]- Are callouts foldable? 
> Yes! In a foldable callout, the contents are hidden until it is expanded.

>[!note]-
Use the following syntax to denote a callout block: `> [!INFO]`.

>[!abstract]-
>Used Mostly for task lists.

>[!info]-
>some stuff here

>[!tip]-
>some stuff here

>[!success]-
>some stuff here

>[!question]-
>some stuff here

>[!warning]-
>some stuff here

>[!failure]-
>some stuff here

>[!danger]-
>some stuff here

>[!bug]-
>some stuff here

>[!example]-
>some stuff here

>[!quote]-
>some stuff here


Currently, supported callout types
| Type     | Aliases                     |
| -------- | --------------------------- |
| note     | note, seealso               |
| abstract | abstract, summary, tldr     |
| info     | info, todo                  |
| tip      | tip, hint, important        |
| success  | success, check, done        |
| question | question, help, faq         |
| warning  | warning, caution, attention |
| failure  | failure, fail, missing      |
| danger   | danger, error               |
| bug      | bug                         |
| example  | example                     |
| quote    | quote, cite                 |



# Templates
>[!caution]
>FOR THE LOVE OF GOD, USE A YAML LINTER!!!
>Any fontmatter errors that are unable to be parsed will cause multiple breaks in the Anki cards plugin.
>The bellow code causes a break because `foo` is unrecognized.
>```
>---
>foo
>cards-deck: DELETE ME
>---
>
>some {1:foo} bar
>```

This is an example that is given
>[!example]
>```
>---
>creation date: <% tp.file.creation_date() %>
>modification date: <% tp.file.last_modified_date("dddd Do MMMM YYYY HH:mm:ss") %>
>---
>
><< [[<% tp.date.now("YYYY-MM-DD", -1) %>]] | [[<% tp.date.now("YYYY-MM-DD", 1) %>]] >>
>
># <% tp.file.title %>
>
><% tp.web.daily_quote() %>
>```

# Banners
https://github.com/noatpad/obsidian-banners
see fontmatter header for this document.
# Anki Integration

>[!warning]
>You must have ANKI open and running to add/remove/modify cards.

## Cards
### deck selection
change the card deck in the header data.
```
cards-deck: C836 - Fundamentals of security
```
There's a way to declare, inline, but it's not organized.

### Card generation
To generate cards, you have to hit 
```
Ctrl + P
FlashCards: generate for current file.
```
The above operation will add/modify/delete cards automatically.

### Front/Back cards
>[!info] card
> Will this card Have A hint? ::yes/no.   ^1661712502430

Will Create:
![[Pasted image 20220828145009.png]]

>[!info] card
>Perhaps as part of a front back style card? ::: possibly? ^1662994560713
> [ ] Convert to Anki [Practice Quiz 3-Q37.png]  (#)PracticeQuiz/Three 


![[Pasted image 20220828154535.png]]


### Cloze Cards
>[!info] card
>This card will become a ==Cloze== card.
^1661712861562
![[Pasted image 20220828145446.png]]

>[!info] card
>This {1:card} will also become a {2:cloze} card.
^1661712861567
![[Pasted image 20220828145509.png]]

#### Hints?
Submitted a request to have Obsidian to Anki  render `{1:something:Hint}`
as a hint.
Apparently `{1:something::Hint}` works. ^1662994560718
>[!info] card
>This {1:card::Hint} will also become a {2:cloze::Hints} card. ^1662994560723
^1662994560729
![[Pasted image 20220912105747.png]]
So Yeah, that works...

# Back links
section is the 2H
- some bullets
^540dd1
- another bullet
and a small sentance to boot.

## Examples

>[!note]
>to render the links text, include a `!`

Pull in the Header and all text to the next header of the same level.
>[!example]
>![[Obsidian Tools and Hotkeys#This section is the 2H]]

Pull in just a single line, the one directly above the reference backlink.
>[!example]
>![[Obsidian Tools and Hotkeys#^540dd1]]

To change the displayed text:
[[Obsidian Tools and Hotkeys#^540dd1|displayed text]]



Still need to figure out how to reference **just** the text inside a text box.

