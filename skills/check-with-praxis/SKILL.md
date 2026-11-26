---
name: check-with-praxis
description: Use for every work task. The user works at a veterinary practice whose AI rules decide what may be done here. Before you write or reply to anything, summarise, translate, answer a clinical or medicines question, work on a patient's case, handle figures, staff matters or marketing, or build a tool, check the task with the Praxis app (check_ai_use) and follow its answer. Skip only small talk.
---

# Check with Praxis first

The person works at a veterinary practice. Its AI rules, held in Praxis, say what this assistant may be given and which tasks are allowed. They apply to every work request, even when the person does not mention the practice or their job.

1. Before starting the task, call `check_ai_use` from Praxis with a `description`: one or two sentences, in your own words, of what the person wants to do, what goes into it and who will read the result. **Put no personal information in it, ever**: no name, address, phone number, email, or record, microchip or policy number. Write "a cat", "the owner", "a colleague". A description with personal details is refused and kept nowhere. Praxis keeps the description and the answer for the practice to review, without the person. You may also send the kind of task, the kinds of information and the reader as hints: name a kind of information only when those details are actually in the conversation or about to be put in, never because the work is about people (a rota formula with no names in it involves no staff details). Never quote a record or the person's words.
2. **Yes**: do the task, and pass on the reminders and conditions in the answer.
3. **No**: say so in one line with the reason Praxis gives. Offer only a way the answer itself names (the task without the personal details, or another tool). If it names none, the task is not done here in any form: not anonymised, not reworded, not as a template.
4. **Already shared**: if the person has already put client or staff personal details in this chat, send `alreadyShared: true`, never the details. If the answer asks them to delete this chat and start again without the details, pass that on, and offer the anonymised version only when the answer offers it.
5. **Not decided**: say so in one line. If Praxis asks for confirmation of rule conditions or exceptions, ask the person each question exactly as returned. Wait for an explicit yes or no to each, then repeat the same check with its confirmation token and their answers in order. Keep the task pending until Praxis answers. If the answer offers a request, call `request_ai_use` with a sentence or two about the task, without names, and the task, information and reader the answer gives in `read`. The person approves it in the confirmation; if none is shown, show the words and wait for their yes. If they decline, nothing is sent.
6. **Praxis did not answer**: say so, and do not assume a yes.

## Practice systems

Use the tools offered on this connection. With optional Systems access, use `get_practice_systems` to read the practice inventory, connected assistant products and visible pending requests. Search by product name to find its catalogue ID. Members may suggest an addition with `suggest_practice_system`. Administrators may add or remove an inventory entry with `change_practice_system`, or approve or decline a pending suggestion with `review_practice_system_request`. The inventory lists software. Changes do not install, connect or uninstall it.

Before a Systems write, show the person the product, the exact action and its effect. Approval adds the product to the inventory. Removing an entry also removes its saved roles and maintenance details. Ask for confirmation in the host or wait for the person's explicit yes in chat before calling the tool. A suggestion records who asked inside Praxis. Send only catalogue and request identifiers, the action and the expected version where required. Reuse the request ID on retry. If the version has changed, read the list again and confirm the new decision.

The assistant cannot read clinical records or change the practice's AI rules through these tools.
