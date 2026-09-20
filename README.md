# triscaler-website

Copyright (c) 2026 Triscaler. All rights reserved.

This repository and everything in it — the page content, copy, layout,
design, HTML, CSS, JavaScript and all artwork including the Triscaler logo,
icons and preview images — is proprietary to Triscaler and is licensed
strictly under the terms in [`LICENSE`](LICENSE).

Nothing may be copied, reused, modified, mirrored or otherwise distributed,
in whole or in part, without the prior written permission of Triscaler.
Unauthorized copying, distribution, modification, or use of this software,
in whole or in part, is strictly prohibited.

## Assets

| file | used for | note |
|---|---|---|
| `logo.png` | header and footer logo | 144px, ~16KB — what the page actually loads |
| `og.png` | link previews on social and chat | 1200px wide |
| `triscaler.png` | master artwork | 1536x1024, the source both others are cut from |

`triscaler.png` was previously referenced directly but never committed, so the
live site was loading a missing image. The page now uses `logo.png`, which is
committed and sized for where it is displayed — a 1.4MB file rendered at 36px
was the entire weight of the page.

Regenerate the derived sizes after changing the master:

```sh
sips -Z 144 triscaler.png --out logo.png
sips -Z 1200 triscaler.png --out og.png
```

## Development

A single static `index.html` with no build step: open it in a browser. No
framework, no webfont, no external stylesheet — the whole page is one file
plus a logo.
