# Codex Custom Pets

Transparent animated companions for ChatGPT Work, with source strips, v2 sprite sheets, motion previews, and QA reports.

<table>
  <tr>
    <th>Mr Grievous</th>
    <th>Dark Dog</th>
    <th>Thauron</th>
  </tr>
  <tr>
    <td align="center"><img src="images/mr-grievous.png" alt="Mr Grievous pet, transparent background" width="240"></td>
    <td align="center"><img src="images/dark-dog.png" alt="Dark Dog pet, transparent background" width="240"></td>
    <td align="center"><img src="images/thauron.png" alt="Thauron pet, transparent background" width="240"></td>
  </tr>
</table>

## Pets

| Pet | Description | Pet ID |
| --- | --- | --- |
| Mr Grievous | Bone-white, horned cyborg mask with watchful red eyes | `pet_6abe49473a888191a4b73eb53bbcdd27` |
| Dark Dog | Dark-iron spiked helm with an ember-red visor | `pet_6abe517a2fe08191b006b1e2134f59e3` |
| Thauron | Dark-armored lord with a towering spiked helm, cape, and greatsword | `pet_6abee113040c8191a4e018abec6cb1f7` |

## Use a pet

### If the pet is already in your account

- In ChatGPT on the web, open **Settings → Personalization → Pet → Select pet**, then choose the pet. It appears in supported ChatGPT Work chats.
- In the ChatGPT desktop app, open your profile menu and choose **Pets**, or open **Settings → Pets**. Choose the pet, then enter `/pet` or use **Show pet** to display it.
- The pet picker changes the appearance of ChatGPT; it does not change how ChatGPT completes tasks.

### Ask Codex to add pets

Because this repository is public, you can ask Codex to use its published pet assets. Open this repository in Codex and paste:

> Add the [character name(s)] pet from this repository to my ChatGPT Pets. Follow `AGENTS.md`, use the matching pet assets and source notes, validate the sprite sheet, then upload and select the pet.

To request a character that is not listed yet, use:

> Create a pet for [character name] in this repository, following `AGENTS.md`. Add its preview and source notes to the README, then validate, upload, and select it in my ChatGPT Pets.

Codex will need access to your ChatGPT Pets tools to upload and select a pet.

### Add one from this repository

1. Download the pet's `spritesheet-extended.png` from its folder under [`pets/`](pets/).
2. In ChatGPT, open **Settings → Personalization → Pet** and choose **Upload pet** if that option is available for your account and surface.
3. Follow the file requirements shown in ChatGPT, then select the uploaded pet.

These sprite sheets use the v2 layout at 1536 × 2288 pixels. The official Pets documentation currently lists the web upload layout as 1536 × 1872 pixels, so some upload surfaces may not accept these v2 files directly. Check the [current Pets instructions](https://learn.chatgpt.com/docs/pets) for the surface you use. The Pet IDs in this table identify pets in the original owner's account; they do not import a pet into another account.

## Files

- `pets/<pet>/spritesheet-extended.png` — final transparent v2 sprite sheet
- `pets/<pet>/source/` — canonical base, generated strips, and included reference art
- `pets/<pet>/previews/` — contact sheet, per-state GIFs, look-direction loop, and MP4
- `pets/<pet>/qa/` — validation, motion, direction, and continuity reports
- `skills/create-pet/` — backup of the pet creation skill and its bundled scripts
- [`AGENTS.md`](AGENTS.md) — repository maintenance and push process

The README portraits in `images/` are transparent PNGs derived from each pet's first idle frame.
