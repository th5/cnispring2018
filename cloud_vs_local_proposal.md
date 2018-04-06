Cost

Third Party

Initially budgeted $6k/yr
Currently projected at $12k/yr
$4,800/yr for servers / compute (CPUs and RAM)
$10,800/yr for storage (hard drives) - projected at 10T (?)

Local
$0/yr for servers / compute
Existing servers have available capacity to handle this. Already paid for.

$26,000 for storage
Expand our existing local storage by 48T x2
This is our current practice. We currently have two of everything for storage. If one went down, we would have a full replacement ready to go.

This is our recommended option.

$13,000 for storage
Expand our existing local storage by 48T
We would not lose data (durability). We have a greater likelyhood of temporarily losing access. Even with just one SAN, there is a lot of redundancy baked in. Many components can fail while still maintaining access.

Either local storage option would be backed up to BMC's separate backup solution.

Currently we have three copies of TriCo-hosted data. One copy in the active SAN. One copy in the fallback SAN. One copy for emergencies in the BMC backup.

Local and hosted storage figures above do not include an additional preservation copy to be hosted with a dark cloud provider, likely Amazon Glacier.

---

TriCo servers (not storage), were budgeted to be replaced this fiscal year for $30k. This is on a four year replacement schedule. Our current servers are meeting our needs and have significant unused capacity. Systems received quotes for new servers in this budget. The quoted servers are only negligably better than our current ones. For these reasons, Systems decided to post-pone replacing the servers for at least a year.

Extending their working life for a couple more years is reasonable. Perhaps those two years of server costs, $15k, could be shifted towards storage. We have enough server capacity but not enough storage capacity.

---

Background

While determining the best path forward, DAMPr considered Islandora a hosted solution. We thought of it as a service that we would pay to access, like signing up for Gmail or 365. While not entirely accurate, this was a useful framing.

Through talking to peer institutions, we later learned additional nuances. We're not signing up for Gmail; we're having an Islandora consulting firm build out a custom repository for us. They specialize in Islandora development so will be able to leverage their experience serving other academic libraries. The five college's Compass repository was highly influential in DAMPr's decision making. The same firm we will be using built Compass and will re-use much of that work as a starting point for us.

Informal feedback from other institutions about Born Digital (parent company: Common Media) have been overwhelmingly positive. Development and support appear to be a la carte which each institution picking what best suits their needs.

We realized that this flexibility also applies to hosting. Born Digital is not a hosting company. If we want to go cloud, they would direct us to an appropriate provider, e.g. Amazon AWS. We would pay Amazon directly for services with no mark-up from BD.

With either cloud or local, BD has provided suggest server specifications, which we plan to follow.

---

Conclusion

All options presented would meet our needs well. 