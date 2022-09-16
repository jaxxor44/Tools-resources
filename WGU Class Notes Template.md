---<%*
  let title = tp.file.title
  if (title.startsWith("Untitled")) {
	  title = await tp.system.prompt("Title?");
  } else {
	  title = tp.file.title
  }
  source = await tp.system.suggester(["HIP4 All-in-one", "Legal and privacy issues Book", "other"], 
  ["HIP4 All-in-one", "Legal and privacy issues Book", "Other"]);
  await tp.file.rename(`${title}`);
%>
aliases: [<%* tR += `${title}` %>]
banner: "![[BinaryScales.jpg]]"
banner_lock: True
created: <% tp.date.now("YYYY-MM-DD  HH:mm:ss") %>
modification date: <%+ tp.file.last_modified_date("YYYY-MM-DD  HH:mm:ss") %>
Template Ver: 2.2
Source: <%* tR += `${source}` %>

tags: C841/<% tp.file.folder() %>
cards-deck: Legal_Issues_in_Information_Security

---
%%
	FUNDIMENTALS:
	- Focus on concepts, and conceptual note taking.
	- use __highlighting__ to _articulate_ points.
	- Have the Key message right up front.
	- Anki cards should be added/edited whenever the note is edited.
	- Link as you go. One good link is worth more than a sentence that can come back. %%
- [ ] expand on <%* tR += `${title}` %>
# <%* tR += `${title}` %>
>[!tip] Key Message

- <% tp.file.cursor() %>

# cards
- [ ] Submit Flash cards to Anki
>[!info] card
>