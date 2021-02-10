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

# Enhancing the Navigation Menu

Recall that this Guide covers only two of the Pages used by the *SunFarm* Customer Application.

Both Pages are described in the **CUSTDSPF** Displayfile which became the ASP.NET Web Page *CUSTDSPF.cshtml" file.

ASP.NET Web Pages are described by the *[Razor Page](https://docs.microsoft.com/en-us/aspnet/core/razor-pages/?view=aspnetcore-5.0&tabs=visual-studio)* syntax, which extends HTML.

ASNA Monarch Nomad&reg; provides *TagHelpers* to repesent DDS equivalent artifacts.

The *TagHelper* that controls the *Active* Functions keys that will be part of the *File* Navigation Menu is:

~~~
<DdsFunctionKeys />   
~~~   

You can find this TagHelper typically at the top of the Page, right under the *DdsFile* TagHelper inside the **HTML* form Tag. 

The following are the first *Markup* lines if the *ASP.NET* Page CUSTDSPF.cshtml:

~~~
<form id="MonarchForm" method="post">
    <DdsFile DisplayPageModel="Model">

        <DdsFunctionKeys />

        <main role="main" class="display-element-uninitialized">
           .
           .
           .
~~~   

*TagHelpers* provide access to class Properties via *attributes* in the markup. Whenever the attribute is nor present, its value takes a *Default*. *DdsFunctionKeys* TagHelper has an attribute called:

~~~
Location
~~~

The default value of *Location* is **VerticalLeft**. Let's change the value such that the *Navigation Menu* is shown at the bottom of the Page[^1].

~~~
<DdsFunctionKeys Location="HorizontalBottom" />
~~~

Build the Application, and run it to see how this small change makes a big difference:
   
   
![Original Page One](/images/dds-funkey-bottom-location.png)


<br>
<br>
<br>

[Continue ...](/remove-redundant-green-screen-info/)


[^1]: Commit "Navigation Menu Customization"