---
title: "Pluggable Page for Shortcode Issue"
date: 2019-02-06T18:02:57-02:00
data: "test"
---

This is a pluggable Page that uses the **Picture** Shortcode specifying the **Path** as Requested Data.

It has a custom FrontMatter Parameter `data`, thus overriding the default one defined in the Header Partial (`head.html`) that'll be used to execute `getJSON`, providing data for the Partial included accordingly to the Shortcode Parameter defined below this line (only one available in this case):

xxx **PICTURE** MASTER SHORTCODE WITHIN A PLUGGABLE FILE BEGIN XXX

Contents of **/partials/picture/path.html** Partial Template:

{{< picture part="path" >}}

<br />
xxx END OF **PICTURE** "MASTER" SHORTCODE XXX