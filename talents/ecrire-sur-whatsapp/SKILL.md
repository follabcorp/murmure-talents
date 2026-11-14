---
name: ecrire-sur-whatsapp
description: Prepare a WhatsApp message and a wa.me link that the person opens and sends themselves. Never sends the message, never reads conversations.
license: MIT
---

# Write on WhatsApp

Prepare a WhatsApp message with the person and give them a link that opens WhatsApp with the text already filled in. The person opens the link and presses Send in WhatsApp themselves. This Talent only prepares the message. It never sends it.

## Gather first

Infer what you can from context and ask one short grouped question for the rest:

1. What the message is for, and the tone wanted (warm, neutral or firm).
2. The recipient's phone number, if the person has it. Otherwise the person picks the contact in WhatsApp.

If a number is given, it must be **complete and in international format**: country code first, then the national number, digits only. No `+`, no leading zero from the national number, no spaces, brackets or dashes. Example: `33612345678` for `06 12 34 56 78` in France. If the country code is missing, ask for it. Never guess it.

## Process

1. Write the text with the person. Keep it short, as suits a chat: a few lines, ideally under 60 words, with one clear request or question if there is one. Show the text and adjust it until the person agrees.
2. Encode the text for a URL (UTF-8 percent-encoding). A space becomes `%20`, a line break `%0A`. Encode `&`, `#`, `?` and `+`, and encode accents and emojis too.
3. Build the link:
   - with a number: `https://wa.me/<number>?text=<encoded text>`;
   - without a number: `https://wa.me/?text=<encoded text>`. WhatsApp then asks the person to choose the recipient.
4. Show the plain text above the link so the person can re-read it, then give the link.
5. Say clearly that the person opens the link and presses **Send** in WhatsApp themselves.

## Examples

With a number (France), the text is "Bonjour, je serai en retard de dix minutes. À tout de suite." :

```
Bonjour, je serai en retard de dix minutes. À tout de suite.

https://wa.me/33612345678?text=Bonjour%2C%20je%20serai%20en%20retard%20de%20dix%20minutes.%20%C3%80%20tout%20de%20suite.
```

Without a number, the text is "Salut ! Tu es dispo ce soir pour un café ?" :

```
Salut ! Tu es dispo ce soir pour un café ?

https://wa.me/?text=Salut%20%21%20Tu%20es%20dispo%20ce%20soir%20pour%20un%20caf%C3%A9%20%3F
```

Then add: "Ouvre ce lien, vérifie le message, puis appuie sur Envoyer dans WhatsApp."

## Guardrails

- Never say or imply that the message is "sent", "delivered" or "sent for you".
- Never claim to send it by another means: no tool, no automation, no WhatsApp Web driven for the person.
- Never read a WhatsApp conversation, chat history or export.
- Never suggest a library, a bot or an unofficial WhatsApp client. WhatsApp's terms forbid them.
- Use only the facts the person gives. Do not invent a number, a name or a date, and mark gaps clearly (for example "[date to confirm]").

Reply in the language the person uses.
