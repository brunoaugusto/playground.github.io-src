---
title: "Shortcode Issue"
date: 2019-02-06T18:02:57-02:00
---

This file calls the **picture** Shortcode to retrieve the Picture Path of the JSON defined in the Header Partial:

---

xxx **PICTURE** "MASTER" SHORTCODE BEGIN XXX

{{< picture part="path" >}}

<br />
xxx END OF **PICTURE** "MASTER" SHORTCODE XXX

---

And now it uses the **include** Shortcode to plug [another Page](/another-page) into this one.

---

xxx **INCLUDE** SHORTCODE BEGIN XXX

{{< include file="another-page.md" >}}

<br />
xxx END OF **INCLUDE** SHORTCODE XXX

---

Both blocks have the same content, proving that calling the "master" Shortcode directly or plugging a Page that the does the same witll work