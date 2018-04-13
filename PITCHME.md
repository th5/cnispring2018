Preservation: An Opinionated Approach

Tom Hutchinson

Bryn Mawr, Haverford, and Swarthmore Libraries

---

Digital Preservation & Conservation

Largely non-technical

Still, many tech and tech-related decisions

---

Fuzzy boundaries

Note: 

Preservation technology considerations aren't isolated. 

Quickly bleed into repositories and lib-tech generally.

---

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

Use what you already have - details:

-One IT dept, potentially two others
-They keep library hardware running (storage and compute), linux sys admin

-IT/College integration - many existing paid-for resources
property, server rooms, power, cooling
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


* Plan for anything failing

Assume any hard drive, any file, any computer, etc will fail at any time. Be ready for multiple simultaneous failures.

Remember, a checksum is a file too. Are you able to tell the difference between a bad file and a bad checksum?

Preservation is great because it's about not losing data (durability). It's not about continuous access (availibility). We get to solve an easier technical problem.


Storage / Preservation / Repository / Backup

Where should the lines be drawn?

I like keeping them separate but interoperating



Why not preservation storage?

No longer a dumb cheap commodity. Move from widely used tech to domain specific solutions. Stops being so cheap. Starts going down in quality.

Precious => locked in


I prefer a preservation layer that plugs into your storage. Keep storage a commodity. Separate out the special bits.

A preservation layer should abstract away the details of storage. I should be able to plug in a variety of different pools of storage.

DIY -> pres platform ->(future) integrated pres
            \-> pres storage



What about preservation within repositories?

This is great. Repositories should be able to perform preservation operations. The additional information a repo has is useful compared with just a bunch of files sitting around.

Pres operations in a repo should be able to be driven externally. I want to plug these into my pres layer too.



I want to preserve both bare files as well as files in repos.



S3 does hashes on hashes on hashes. Isn't that preservation?

It's better than them not using hashes. It is not preservation.

Choose technologies that put in safeguards against data loss, such as ZFS and S3. Still assume that these are just as unreliable as the external hard drive in your desk which one day will not turn on.

Preservation requires a paper trail. We need verifiable records. We need to be able to audit.

We don't have to choose between state of the art storage and preservation. Keep the magic in the storage. The interface that storage should present to preservation is it's lowest common denominator, plain old files. Any storage should be easily plugged in as they can all handle this.



Isn't cloud storage cheap?

Cloud storage providers have been in aggressive price wars. New entrants (Oracle) with deep pockets are paying highly to undercut existing players. At some point (now?) prices will stop dropping. Those that figure out how to profit (or at least not bleed money) at current levels will outlast the others. If they can't do that some firms will be able to afford to operate storage without bringing in a lot. Competition will cool down. Prices will stop dropping. They may rise. They may even rise as dramatically and quickly as they fell.

When things start changing, will you be able to handle it?




Storage is a dumb commmodity. It should be cheap and unremarkable. It shouldn't matter if it's local or hosted.


Here is an example of cheap

The cloud hosting company Backblaze publishes the design for their own storage hardware. It's just a big computer with as many consumer grade hard drives as they can pack in. You can buy one from a vendor or build one yourself. ~$10k will get you a quarter petabyte (1P = 1000T)

How does your annual cloud storage bill look compared with that? How much storage are you getting for it?





Hosted vs Enterprise vs White Box vs DIY

What do you need? Up-time, redundancy, support, ...

Sticker costs vs staff time






Cloud: 

What's all the fuss?


In the tail end of a start-up tech bubble. Rates are low, borrowing is cheap, saving is expensive. Massive investment shift to new tech companies. Tech giants are now the most profitable and powerful companies in the world.


Start-ups and tech juggernauts driving the conversation


They produce some great technology. When separating the wheat from the chaff, important to understand forces at work where all this tech is coming out of. When these situations greatly differ from our own, there can be a high impedence mismatch.


Big tech is operating at an unprecedented scale. They had to create the knowledge and tools to scale that much. Automation created was a necessity. When at smaller scale, many problems are solved more easily with methods that won't massively scale.

For instance, analysing data that can fit on a laptop with Big Data tools is an undue burden.



Start-ups

They start with nothing. They don't have software, web sites, staff, infrastructure, users...

Cloud hosting (AWS) is a great way to get going with little initial investment.

Starting from scratch. Repeated failure. Often heavily dependent on relatively new engineers - work 'em to the bone. New engineers there have large role in tech decisions. Rapid reinforcing cycle of iterating through new disposable tech [reword]. Lots of shiny objects. Lots of complex tooling. Re-solving many old problems poorly.

Every time I hear [some engineer] say that libraries should be run more like start-ups, a dagger goes straight into my heart. No! NO NO NO!!!

Model ourselves off of get-rich-quick schemes? Off of sweatshops that aim to create nothing of value?

At the very least, their technology decisions are informed by wildly different incentives (right word?).

They aim to scale. Today no users, tomorrow a million. If your app is architected to scale, cloud providers can handle it. They offer many out of the box tools needed to scale.

Low up-front costs. Only pay for more once you have the users.


This flexibility isn't free. For a given level of resources, 


The cloud isn't like the regular computing we are used to. Basically everything we are familiar with has been fundamentally altered to be able to scale.

Any individual cloud computer can go down at any time. Your massively scalable app is meant to be able to handle those failures.

Storage is weird. We are used to network resources feeling like local resources (eg using files on the "R drive"). We don't have to worry about those two being different because they behave the same to us. Object stores are different and lame.



A couple notches down from the tech giants are still quite large users. If you are operating at the data center level, "the cloud" can be a good value.




Virtualization is sub-dividing a fixed pool of resources. In the cloud that fixed pool is much larger than one org will use. However same technologies can be applied to local hosting. Still get to chop up, spin up, tear down. Many flexibility benefits able to be realized using similar technologies locally.

Difference: cheaper over life, pay up front, fixed limits



To be honest I'm cloud-agnostic. I'm not anti-AWS (other than Amazon treating fulfillment workers terribly until they can be replaced by robots and being generally anti-worker). I simply encourage decision-making with open eyes. It's not magic; it's just other people's computers.

It feels like many IT directors don't want to get left behind. "Transitioned org to the cloud", "Oversaw adoption of AWS" never looks bad on their resumes. There are other forces at play above my pay grade.

All I know is that if you aren't careful, it's easy to be sold a bill of goods. "Modern" and "efficient" are codewords for overly complex solutions that cost more, require more staff, and do less.


We can still reap the rewards of tech advances. For us, doing so involves cutting through the hype to examine what's available and what would be a good fit.


Runnable recipes is a big win. Like virtualization, this is a development has can potentially be a real improvement over the old way of doing things. It isn't magic. It shifts a current problem somewhere else. Instead of maintaining notes, you are maintaining recipes. Gains in efficiency often come at a high cost in configuration. Even tool selection is difficult as there are many overlapping technologies, often used in conjunction.


I recently went to a workshop. We performed what would otherwise be a complex installation quickly by using a pre-written runnable recipe. Sounds good. The reality was an absurd series of Russian nesting dolls. 

Computer < Vagrant < Docker

The workshop hosts aim to improve the process by adding Ansible.

How many runnable recipes do I need?!




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

No Single Tech

No Piling on Tech




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
