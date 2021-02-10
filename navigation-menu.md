---
layout: page
title: Navigation menu
permalink: /navigation-menu/
---

Legacy IBMi Applications were *typically* navigated using keyboard special keys. We are talking about the **F** (or *Function*) keys IBM keyboards have on top of the keyboard. 

Pages are described in *Displayfile*s on the IBMi Platform using a language called DDS.

A *Displayfile* describes one or more *records* (sections of a page), where the developer can inidcate which of the *Function* keys are *Active*, keys that are allowed for the operation and navigation of the page.

It became a common practice to show such *active* keys as constant labels on the Page, where the label would show the number of the *Function* key and a short description of it's related command. Refering back to [Guide Objective](/guide-objective) where we have shown the *Original Page One*, you can see a constant label at the bottom that reads:

~~~   
F3=Exit
~~~   

In addition to *Function* keys, there are other *Aid* keys used for navigation, such as: **Enter**, **PageUp** and **PageDown**. These are typically **not** presented along with the *Function* keys when they are active (*Enter* is reserved to **Submit** the Page for processing)

During Migration *ASNA Monarch Cocoon for Nomad&reg;* will use DDS keywords to extract *Active* aid keys and present them as a Navigation menu (to the left of the Page). Different to typycal IBMi legacy pages, the **Enter**, **PageUp** and **PageDown** navigation buttons will be presented, in case the Device being used, does not have an attached keyboard, such as a *Tablet* or a large *Smart Phone*.

The DDS keywords had limited space to describe the *Active* aid keys, and the Text was optional, in which case the Migration cannot help to improve the label on the Navigation Menu item.


<br>
<br>
<br>

[Continue ...](/remove-redundant-green-screen-info/)