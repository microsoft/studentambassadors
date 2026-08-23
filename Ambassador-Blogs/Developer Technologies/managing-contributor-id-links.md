# Simplifying Microsoft Learn Contributor ID links for Student Ambassadors
### Thiago Kusal | LinkedIn- @tkusal

Sharing technical content from Microsoft Learn is a core activity for many Student Ambassadors. To measure the impact of these shares, Microsoft provides a **Contributor ID**. When appended correctly to URLs, this ID helps track engagement and ensures your contributions to the community are recognized.

However, adding this parameter isn't always straightforward. Locale codes, existing query parameters, and manual formatting can lead to broken links or untracked metrics. In this guide, we'll explore what the Contributor ID is, how to structure it correctly, common pitfalls to avoid, and how to automate the process.

## What is a Contributor ID?

A Contributor ID is a unique identifier assigned to Microsoft Learn Student Ambassadors (and other Microsoft community members) to track the reach of the content they share. When a user clicks a link containing your ID, the engagement is attributed to you, which is often used as a metric for program milestones and impact reports.

## How to correctly add your Contributor ID

The tracking parameter used by Microsoft Learn is `wt.mc_id`. To append it to a URL, you simply add it as a query parameter.

The structure of the ID itself often follows a specific format provided by your community manager (e.g., `studentamb_YOURID`).

**Example:**
If the original link is:
`https://learn.microsoft.com/azure/virtual-network/virtual-networks-overview`

You append the parameter using a question mark (`?`):
`https://learn.microsoft.com/azure/virtual-network/virtual-networks-overview?wt.mc_id=studentamb_YOURID`

## The problem with localized URLs

When browsing Microsoft Learn, you might notice that URLs often include a locale code, such as `en-us` or `pt-br` (e.g., `https://learn.microsoft.com/en-us/azure/...`). 

**Why is this a problem?**
If you share a link with a hardcoded locale like `en-us`, a user from Brazil clicking the link will be forced to read the content in English, even if a Portuguese version is available. 

**The best practice:**
Always remove the locale code from the URL before sharing it. Microsoft Learn will automatically redirect the user to the appropriate localized version based on their browser settings, while preserving your `wt.mc_id`.

**Incorrect:** `https://learn.microsoft.com/en-us/azure/virtual-network/?wt.mc_id=studentamb_YOURID`
**Correct:** `https://learn.microsoft.com/azure/virtual-network/?wt.mc_id=studentamb_YOURID`

## Dealing with existing query parameters

URLs often already contain query parameters, such as search terms, session IDs, or pagination. You can identify them by the presence of a question mark (`?`) in the URL.

If the URL already has a `?`, you must append your Contributor ID using an ampersand (`&`) instead of a question mark. Adding a second `?` will break the URL.

**Original URL with existing parameter:**
`https://learn.microsoft.com/search/?terms=azure`

**Correctly appended Contributor ID:**
`https://learn.microsoft.com/search/?terms=azure&wt.mc_id=studentamb_YOURID`

## Common errors to avoid

1. **Double question marks (`??`)**: Using `?` when the URL already has parameters.
2. **Missing the query prefix**: Forgetting the `?` or `&` entirely (e.g., `...overviewwt.mc_id=...`).
3. **Hardcoding the locale**: Keeping `en-us` or other language codes in the shared link.
4. **Typographical errors**: Misspelling `wt.mc_id` (e.g., `wt_mc_id` or `wt.mc.id`).

## How to validate your link

Before sharing your link broadly, it's a good idea to test it:
1. Open an incognito or private browsing window.
2. Paste your finalized URL and press Enter.
3. Check the address bar after the page loads. The `wt.mc_id` parameter should still be present in the URL, and the page content should load successfully in the correct language.

## Automating the process

Formatting links manually every time you want to share a piece of content can be tedious and prone to errors. To solve this, I developed an open-source browser extension called the **Ambassador Referral Linker**.

This tool sits in your browser and automatically:
- Removes locale codes (like `/en-us/`) to create neutral URLs.
- Appends your pre-configured `wt.mc_id` parameter.
- Intelligently handles existing query parameters (`?` vs `&`).
- Copies the ready-to-share link directly to your clipboard with a single click.

You can check out the source code, contribute, or install the extension from the GitHub repository:
[github.com/tkusal/ambassador-referral-linker](https://github.com/tkusal/ambassador-referral-linker)

> **Disclaimer:** The Ambassador Referral Linker is an independent, community-driven open-source project and is not an official Microsoft product. It was built by a Student Ambassador to help the community streamline their sharing workflow.

Sharing knowledge is a big part of what we do. By ensuring our tracking links are formatted correctly and efficiently, we can focus more on the content and less on the query string mechanics!
