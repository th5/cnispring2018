Preservation: An Opinionated Approach

Tom Hutchinson

Bryn Mawr, Haverford, and Swarthmore Libraries

---

Digital Preservation & Conservation

Largely non-technical

Still, many tech and tech-related decisions

+++

Fuzzy boundaries

Preservation technology considerations aren't isolated.

Quickly bleed into repositories and lib-tech generally.

<!-- Many decisions impact much more than preservation -->

<!-- 
Revise language. Convey that some digi pres tech decisions
also are wider lib-tech decisions
 -->

<!-- Many decisions are not isolated to digi pres. Best if made
among wider lib-tech needs. -->

<!-- +++

Case study of my institutions hopefully more broadly applicable -->
<!-- cut saying explicitly? -->

---

Pleasantries

Hats off to lib-tech community

Hats off to TriCo, particularly directors and their radical management style (future presentation?)

---

Principles

* UNIX philosophy: narrow composable components

We see this in practice in other apps

Most of ours are made up off-the-shelf broadly reusable components. Most commonly:
web server (httpd, nginx), database (Postgre), search engine (Solr, Elastic)

When needs require, components can generally be swapped out for something better suited. For instance as an app grows, it may be necessary to move the database on to it's own server, to multiple servers, etc.

Components can be selected for other reasons. We use Apache httpd for everything. This let's us reuse our experience and allows us to sufficiently deepen our working knowledge.

Lower technical debt/costs than do everything monoliths. 

* Go together

Narrow focus of components keep them broadly reusable, not just within an organization but across mainy industries. We greatly benefit from solving common problems together. 

Take Postgre. Instead of working within a single organization or even within the lib-tech community, we leverage the work of practically anyone trying to store and retrieve data. This is orders of magnitude different and cannot be understated.

* Use what you already have

people, infrastructure, knowledge, hardware, etc

<!-- 
case study on trico
spell out what you have to work with already     
-->

-One IT dept, potentially two others
-They keep library hardware running (storage and compute), linux sys admin

-IT/College integration - many existing paid-for resources
server rooms, power, cooling
IT staff
  support as linux sys administration
  round the clock support of critical infrastructure
    network
    physical hardware
      compute
      storage
    virtualization stack
  lots of applicable experience: running apps, choosing technologies, etc
    (often left on the table)

Library staff
  knowledgable about repositories
  knowledgable about non-technical and technical preservation practices
  abreast of developments within the field: hungry to make things happen, high bar of what is possible


* Does it fit?







Cloud: 













Observations

Decisions






Need

Bridge people: speak both IT and librarian

So close already you can taste it
Still, too easy to speak past each other and feel divided

"What do they mean when they say preservation storage?"

"A backup is not preservation!"








Budget

Financial

Even with most robust endowments in the nation, very cost conscious.

Limited engineering staff => limited technical budget. We can only know/do so much. Quite constrained in development time.

Even staff at large universities pale in comparison to armies of people who make commonly available apps that are users are accustomed to (gmail, word).




No Magic Bullets

No Magic

No single tech




Keeping data long-term isn't a library specific problem. Making data useful isn't a library problem either. Why are we trying to solve them ourselves? If we are blazing the trail, why isn't the rest of the world following along?

We know the value of using the world's solutions. Perhaps we should consider the value of solving the world's problems. Can archive.org be the only thing of value we have to offer? What gains could be realized by broadening our solutions?





Many lessons to take away from DAMs

Fedora 3 to 4 extremely painful, particularly for early adopters who customized heavily to add functionality not yet standard.

[The application formerly known as] Hydra <Prince symbol?>

Extremely powerful => will check all boxes on many system comparison charts

Administrators can hear it as one thing to solve all of our problems

In practice, many institutions are spinning their wheels and not getting all that far.

Most of us have simple straight-forward requirements. Why isn't this already a solved problem?


Line 




---

UNIX

---

Storage: Dumb Commodity

---











Hosting

Storage











---

Situation:
Many "repos". Each may serve particular purpose. 
Purpose may be related to repos features. However likely also strong
historic reasons.

---

Get a lay of the land:

* Which systems do you have now?
* What is in each?

+++

Get a lay of the land:

* How do users *feel* about the systems?
* Repos are easy to start, hard to kill.
* Likely too many, with several disliked.

---

Know your user:

* What do they say they want?
* What do they actually want?
* *Listen!*

+++

Know your user:
<br>
Which do they like? Why?
<br>
What do they need?
* Viewers
* Particular metadata support
* Workflow
* Permissions

+++

Know your user:

* Are there any installations that they like?
* Don't limit this question to only your institution.

+++

Know your user:

* What are they saying they need?
* Buzzwords?
  * Linked data / RDF / triplestore

+++

Know your user:

* Are there other systems they want to integrate with?
* What protocols do they speak? OAI-PMH?

+++

Know your user: Hosted vs local?

* Perception vs reality
* Hosted solutions often solve the easy problems. Leaving your team to work on priorities
* On the other hand, hosted often solves the easy problems

+++

Know your user:

* What system/s do they say they want?
* Reasons?
* Which features?

---

Know your enemy:

* What other systems are being considered?
* Where are the major features of other systems?

+++

Know your enemy:

The project formerly know as Hydra-Fedora

* Administrators hear how powerful it is, assume can solve all their problems.
* No magic bullets!
* No shortcuts around *the work*
* Great project btw, Fedora is really solid

p.s. linked data is slow...

+++

Know your enemy:
Hydra-in-a-box (Hyku)

* Vaporware
* Spent whole time on naming??
* I know I'm in minority with this. Huge respect for their team.

+++

Know your enemy:

What features are your users talking about, hearing from sales reps, colleagues, etc?

DSpace has many features that others tout as new or advanced. Sometimes
different terminology is used.

+++

Know your enemy:

e.g. a commercial hosted offering is selling itself as able to
"use any metadata standard". Compared to DSpaces built-in Dublin Core
this sounds more advanced. However what they actually meant is that you
could write a cross-walk from any standard to their internal metadata model.
DSpace already has that!

---

Hearts and minds

Librarian vs IT
Often saying same thing, just speak different languages. Cloud can be seen as
way to get around IT ("those people think preservation is making a backup!?").

Build bridge people! So desperately needed

---

Learn DSpaces capabilities

Learn benefits
* Not just a pile of code. Duraspace is crucial supporting infrastructure.
* Robust commercial development community
* Excellent practical documentation
* Attentive to needs of small institutions!

---

What would be best for us?
* Ideal repo for my institutions doesn't exist
* DSpace + theme + media players (+ a little custom dev ?)
* Instead of paying for expensive product/hosting, consider paying dev time

---

Know DSpaces downsides
* Permissions, e.g. search snippets don't respect perms
* "Add-ons" require development (not one-click to add player, etc)
* Time it takes to admin installation, whether local or hosted
* Default theme visually uninspiring
* No buzz. This isn't a joke. Prominent vaporware has a lot more hype
surrounding it.
