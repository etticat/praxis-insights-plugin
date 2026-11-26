# Praxis Vets

![Praxis](./assets/praxis.svg)

**Preview package.** The AI rules endpoint and these directory listings are awaiting activation.

Your veterinary practice's AI rules, inside the assistant you already use. Before a work task, the assistant checks it with Praxis and tells you whether your practice allows it here (Yes, No or Not decided), what this assistant may be given, the reminders your practice wants said, and the allowed way when the answer is No. If a task is not decided yet, it can send your practice a request, which you approve first. Each member of staff connects their own assistant to their practice in Praxis. The connection reads the practice's rules and Praxis's guidance for vet practice work. With optional Systems access, it can read the practice’s software inventory and suggest additions for review. Administrators can also change the inventory and review suggestions. Each change asks for confirmation. Clinical records stay outside the connection. Practice managers change AI rules in Praxis.

Package identifier: `praxis-vets`.

Connect the remote Praxis server through your host's OAuth connection flow at https://praxisvets.com/mcp/ai-use. Sign in to Praxis as yourself, confirm your practice and the assistant you are connecting, and grant only `ai-use`. Do not paste account credentials or tokens into chat. The bundled check-with-praxis skill asks Praxis before each work task. A Praxis account at a practice that uses Praxis is required.

The package contains the skill and public connection metadata. The service runs remotely; the public plugin repository contains no Praxis backend and no practice records.

Praxis signs you in and keeps a record of your connection: your practice, you, the assistant and account you chose and your job, with the connection's token stored only as a hash. A check sends a short description of the task without personal details. Praxis keeps screened descriptions and anonymous check counts. A request you approve sends your practice's managers your name and the words you approved. With optional Systems access, the assistant can read the practice’s tracked software and connected assistant products, and submit a catalogue addition for review. Members can see their own pending suggestions. Current administrators can also see pending suggestions from colleagues, approve or decline them, and add or remove a system from the practice inventory. Each write asks for your confirmation. The tools cannot change practice AI rules or read clinical records. Removing the connection in Praxis stops its access. The bundled skill sends no data to services other than its declared Praxis connection.

Privacy: https://praxisvets.com/privacy

Support: https://praxisvets.com/support

Terms: https://praxisvets.com/terms

Version 0.2.0. Proprietary; all rights reserved.
