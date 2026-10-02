---
name: rovzu-library
description: Work with the user's Rovzu reading library. Use when the user mentions Rovzu, their reading list or saved articles, or asks to find, read, summarize, open, save, finish or archive something they saved to read later.
---

# Using Rovzu

Rovzu is the user's personal library of saved links: articles they mean to read, videos, posts and more. Each item is on one list: pending (saved, not finished yet), finished, or archived (set aside). Reach it through the Rovzu connector's tools.

## Find what they saved

- To find items about a topic, call `search_library` with the words that matter. It matches titles, sites and the articles' text, and returns the passage that matched.
- To answer what is on a list ("what's pending?"), call `list_items`. Lists come newest first.
- When the user wants to browse or manage their whole library, call `open_library`, which opens it at full screen.

## Read

- When the user wants to read, open or see an article themselves, call `open_article`. It shows the article in Rovzu's reading view at full screen. Do not paste the article into the conversation.
- When the user asks about an article (a summary, a comparison, a quote), call `read_article` and answer from its text. Quote faithfully, and name the item by its title with its `rovzu_url` link.
- If `read_article` says the text is `preparing`, Rovzu is still fetching it: say so and try again in a minute. If it is `unavailable` or `none` (a video or a post), offer the original link instead.
- If it says `hidden_while_studying`, the user is studying that article in Rovzu, writing what they remember of it. Do not recover, rebuild or guess its text in any way. Suggest finishing the study in Rovzu.

## Save and organize

- Save the links the user asks to save with `save_links`, up to 10 at a time. Say which were saved and which were already in the library.
- Move items between lists with `update_item`: finish, reopen, archive or unarchive.
- Nothing can be deleted from the conversation. When the user asks to delete items, tell them deleting is done in Rovzu itself and offer to archive them instead. Do not look for another way to delete them.

## Answer

Answer in the user's language. Keep lists short, lead with titles, and never show raw tool output.
