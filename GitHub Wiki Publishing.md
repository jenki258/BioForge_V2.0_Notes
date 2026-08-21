# GitHub Wiki Publishing

#BioForge #BioForge_V2_0 #Wiki #Maintenance

The editable documentation source is the `Github` directory in the BioForge Ideas vault. A synchronized publishing clone is generated beside it as `GitHub-Wiki`.

## Publishing workflow

1. Edit and validate the canonical `Github` pages.
2. Verify that each Markdown file begins with one H1 heading.
3. Validate every wiki-style link against a page filename.
4. Synchronize the complete tree into `GitHub-Wiki`.
5. Push the contents of `GitHub-Wiki` to the repository's `.wiki.git` remote.
6. Open Home, sidebar links, nested content pages, code blocks, tables, and anchors on GitHub after publishing.

`_Sidebar.md` and `_Footer.md` are GitHub Wiki control pages. Keep catalogue pages as the stable navigation layer instead of adding hundreds of individual content links to the sidebar.
