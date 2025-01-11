---
{"dg-publish":true,"permalink":"/projects/school-fall-2024/obsidian-school-vault/"}
---


The school sharing system from last year was clunky and annoying, so I want to switch it up this year. 

# Obsidian school design

- I need to be able to see all due dates
- I need to see each kid's copy of the assignments/checklists separately
- I want to replay my edits over theirs without overwriting their checklist status

## Scripting setup

- I use obsidian sync to view their vaults. I never pull their content into my vault
- I use git diff to generate a patch file, then `patch -p1 [patchfile]` in each of their vaults to apply it

### hangups

- obsidian-git autocommits a LOT, so I will have to make a patch based on the date somehow in order to get all of the relevant changes
- 
