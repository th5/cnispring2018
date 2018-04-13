Preservation: An Opinionated Approach

Tom Hutchinson

TriCollege Libraries
Bryn Mawr, Haverford, and Swarthmore Colleges

---

Digital Preservation & Conservation

Note:

Largely non-technical

Organizational, financial

Still, many tech and tech-related decisions

---

Fuzzy boundaries

Note: 

Preservation technology considerations aren't isolated. 

Quickly bleed into repositories and lib-tech generally.

---

UNIX
Broadly reusable composable pieces

---

UNIX
Narrow constrained

grep

---

UNIX
Narrow constrained

Fedora

---

Composable components

web app

Note:
web server, database, search
apache, postgres, solr

---

No Magic

Sales

+++

No Magic

Hype

+++

No Magic

One technology to solve all your problems

---

Rant On The Cloud

Start-ups

Note:

+++

The Cloud

Datacenter Scale

Note:

Netflix

---

Use What You Have

Case Study: TriCo

Note:

land, server rooms, power, cooling, redundant high speed internet, servers, virtualization stack, storage hardware, backup system

lots of applicable experience between web dev team and IT: running apps, choosing technologies, etc

+++

Use What You Have

Case Study: TriCo

Staff: IT

Note:

24x7 IT covering basic infrastructure

Linux system admin

+++

Use What You Have

Case Study: TriCo

"Web development" team

+++

Use What You Have

Case Study: TriCo

Library staff
  knowledgable about repositories
  knowledgable about non-technical and technical preservation practices
  abreast of developments within the field: hungry to make things happen, high bar of what is possible

+++

Decision: expand local storage, make full local copy, assets and metadata in commodity dark cloud

Note:

Get in on temporary price war. Be ready to get out. Storage should be a dumb cheap commodity.

+++

Vision for 2.0

Note: copy at each of the TriCo, fullfilled however they want, plus one off-site

Lot of resistance to idea of because of NDSA criterion of geographic distribution

---

Q & A



---

~~RANTS!~~ Opinions

Build bridge people

Note:

Folks who speak both librarian and IT

+++

~~RANTS!~~ Opinions

Plan for anything failing

Note:

Assume any hard drive, any file, any computer, etc will fail at any time. Be ready for multiple simultaneous failures.

Remember, a checksum is a file too. Are you able to tell the difference between a bad file and a bad checksum?

Preservation is great because it's about not losing data (durability). It's not about continuous access (availibility). We get to solve an easier technical problem.

+++

~~RANTS!~~ Opinions

Storage / Preservation / Repository / Backup

Where should the lines be drawn?

Note:

I like keeping them separate but interoperating

+++

~~RANTS!~~ Opinions

Why not preservation storage?

Note:

No longer a dumb cheap commodity. Move from widely used tech to domain specific solutions. Stops being so cheap. Starts going down in quality.

Precious => locked in


I prefer a preservation layer that plugs into your storage. Keep storage a commodity. Separate out the special bits.

A preservation layer should abstract away the details of storage. I should be able to plug in a variety of different pools of storage.

DIY -> pres platform ->(future) integrated pres
            \-> pres storage

+++

~~RANTS!~~ Opinions

What about preservation within repositories?

Note:

This is great. Repositories should be able to perform preservation operations. The additional information a repo has is useful compared with just a bunch of files sitting around.

Pres operations in a repo should be able to be driven externally. I want to plug these into my pres layer too.

I want to preserve both bare files as well as files in repos.

+++

~~RANTS!~~ Opinions

S3 does hashes on hashes on hashes. Isn't that preservation?

Note:

It's better than them not using hashes. It is not preservation.

Choose technologies that put in safeguards against data loss, such as ZFS and S3. Still assume that these are just as unreliable as the external hard drive in your desk which one day will not turn on.

Preservation requires a paper trail. We need verifiable records. We need to be able to audit.

We don't have to choose between state of the art storage and preservation. Keep the magic in the storage. The interface that storage should present to preservation is it's lowest common denominator, plain old files. Any storage should be easily plugged in as they can all handle this.

+++

~~RANTS!~~ Opinions

Talk to your computer science departments

Note:

+++

~~RANTS!~~ Opinions

Talk to your computer science departments

coding theory, information theory

Note:

+++

~~RANTS!~~ Opinions

Know your materials

How to debug tofu

ASCII et al, UTF-8

Note:

Just like if you were working with paper

+++

~~RANTS!~~ Opinions

Use error correcting codes for better fixity checks

parchive, others

Note:

Fixity using checksums/hashes good. Those plus backups gets us very far.

However not perfect. 

+++

~~RANTS!~~ Opinions

Use error correcting codes for better fixity checks

parchive, others

erasure codes, Reed-Solomon

Note:

Built into RAID, ZFS, ECC memory. Pick technologies like those but don't rely on the magic parts. Still assume fragile. 


