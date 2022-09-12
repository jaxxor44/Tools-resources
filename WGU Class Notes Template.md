---<%*
  let title = tp.file.title
  if (title.startsWith("Untitled")) {
	  title = await tp.system.prompt("Title?");
  } else {
	  title = tp.file.title
  }
  source = await tp.system.suggester(["ITIL Foundation, 4th ed.","Dion Training","Udemy", "LinkedIn","YouTube"], ["ITIL Foundation, 4th ed.","Dion Training","Udemy","LinkedIn","YouTube"]);
  await tp.file.rename(`${title}`);
%>
aliases: [<%* tR += `${title}` %>]
banner: "![[project workers.jpg]]"
banner_lock: True
created: <% tp.date.now("YYYY-MM-DD  HH:mm:ss") %>
modification date: <%+ tp.file.last_modified_date("YYYY-MM-DD  HH:mm:ss") %>
Template Ver: 2.0

Class: C846 - Business of IT
Source: <%* tR += `${source}` %>
tags: C846/<% tp.file.folder() %>
cards-deck: C846 - Business of IT::<% tp.file.folder() %>

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

[[ITIL Foundation, ITIL 4 Edition (Book).pdf#page=00|ITIL Foundations Book]].
- <% tp.file.cursor() %>

# Examples
>[!example]- Axle Car Hire 🏢
>👨Henri, the CEO:
>👩 Su, the Product manager:
>👵Radhika, IT business analyst:
>👲Marco, IT deliver manager:
>Customers:
>👩‍🎓Ichika, The Student:
>👳Faruq, The Retiree:
>👩‍💼Amelia, The Facilities Manager:

# cards
>[!info] card
>