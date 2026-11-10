# LexWeave Lookup for Obsidian

Reading English in Obsidian and stuck on a word? Double-click it in reading view
or in a PDF (or, while editing, select it and run "Translate Selection in Popup"),
and a card tells you what it means in that sentence, in your own language, with
its pronunciation (IPA) and a button to hear it.

- **A word you don't know**: the meaning that fits the sentence you are reading,
  not just the first one in the dictionary.
- **A phrase or a whole passage**: a translation sentence by sentence, the
  phrases worth knowing in it, and answers to your questions about any part of
  it (grammar, usage, culture, or your own question).
- **A PDF opened in Obsidian**: the same, in Obsidian's own PDF viewer. You can
  also hold Control and point at a word.
- **Something worth keeping**: save it to a review note in your vault, or insert
  the meaning right after the word in your note.

## What you need

- **A Gemini API key from Google**, which you create in Google AI Studio with a
  Google account and paste into the plugin's settings. The settings walk you
  through it.
- Optional: a Google Cloud key for Cloud Translation, and one for Google's cloud
  voices. Without them the plugin uses Gemini for translation and your device's
  own voices for reading aloud.

## Before you install: what this plugin does and doesn't do

Obsidian asks plugins to state these plainly.

- **Source code: not public.** The plugin's source code is kept in a private
  repository. Obsidian's community directory reviews it there and checks that
  every release here is built from it. This repository holds only the release
  files.
- **Payment: the plugin is free; Google's services may not be.** Lookups go to
  Google's APIs with your own keys. Whether Google charges you depends on the
  plan you have with Google and how much you use; any charge is between you and
  Google. LexWeave receives nothing from it.
- **Account: a Google account is needed** to create the Gemini key. There is no
  LexWeave account.
- **Network use: only Google, and only for what you ask.**
  - **Gemini API** (`generativelanguage.googleapis.com`): the text you look up,
    the sentence before and after it (a setting lets you send only the sentence,
    or the whole paragraph), and any question you ask about it. This is how the
    meaning, translation or answer is made.
  - **Cloud Translation API** (`translation.googleapis.com`), only if you add
    its key: a passage to translate when Gemini is unavailable.
  - **Cloud Text-to-Speech API** (`texttospeech.googleapis.com`), only if you
    choose Google's voices and add its key: the text to read aloud, and a request
    for the list of voices.

  Everything goes straight from Obsidian on your device to Google. There is no
  LexWeave server in between.
- **Files outside your vault: none.** The plugin reads and writes only inside
  your vault: its settings file, and the notes you choose to save to or insert
  into.
- **Your API keys are in your vault.** Like every plugin's settings, they are in
  `.obsidian/plugins/lexweave-lookup/data.json`. If your vault is synced or
  shared (Obsidian Sync, iCloud, a git repository...), the keys go wherever the
  vault goes.
- **No ads, no analytics, no telemetry.** The lookup history and caches stay in
  Obsidian's storage on your device and are never sent anywhere.

Privacy policy: https://lexweave.me/legal/lookup-privacy (see "The Obsidian
plugin").

## Licence

Free to install and use; all rights reserved. See [LICENSE](LICENSE). A few
helper functions from esbuild, the bundling tool, come with their own notice in
[THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md).

LexWeave Lookup is an independent project. It is not made or endorsed by
Obsidian.
