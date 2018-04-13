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

Fixity using checksums/hashes good. That plus backups gets us very far.

However not perfect. 

+++

~~RANTS!~~ Opinions

Use error correcting codes for better fixity checks

parchive, others

erasure codes, Reed-Solomon

Note:

Built into RAID, ZFS, ECC memory. Pick technologies like those but don't rely on the magic parts. Still assume fragile. 


