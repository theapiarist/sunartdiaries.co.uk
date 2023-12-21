---
categories: 
  - fauna
date: 2019-06-01
draft: 'false'
tags:
  - Morvern
  - Loch Sunart
  - Acharacle
title: 'The birds of Ardnamurchan'
---

Ardnamurchan has excellent birdwatching. In a relatively small area it has a variety of habitats - mountain, moorland, all types of woodland, raised bog, coast, sea and freshwater lochs, machair and just about everything in between.

Bird Watching magazine [published are article on birdwatching on Ardnamurchan](/pdfs/Bird-Watching-2013-article-on-Ardnamurchan-Birds.pdf) in 2013 calling it _Scotland's Hidden Gem_.

{{< figure src="images/190506-053-2.jpg" caption="Blue tit" alt="Blue tit" >}}

I'm an amateur, but enthusiastic, birdwatcher. Like many birdwatchers I try and keep a running list [^853] of what I see locally (my patch) and on my travels.
[^853]: In my head ... I'm not organised enough to write it down.

I'm not a [_twitcher_](https://www.britishbirdlovers.co.uk/bird-watching-for-beginners/what-is-a-twitcher). I don't chase rarities, I don't keep monthly, annual or geographic records. I'm hopeless at discriminating between most of the _Phylloscopus_ (leaf) warblers (and gulls [^219]). I do however have a vague idea of the - very extensive - list of UK birds I have **never** seen and enjoy reducing the number when I have the chance.
[^219]: Though I **can** tell the difference between a Chiffchaff and a Greater Black backed Gull ... it's the call isn't it?

It's always good to know what **might** be seen in a particular area _i.e._ what has been seen before and is therefore likely to turn up again.

Or that's there all the time if I was only a bit more observant ;)

## The BTO open mapping bird atlas data

Fortunately, thanks to thousands of volunteers and the [British Trust for Ornithology](https://www.bto.org), there are outstanding records of overwintering and breeding birds for the entire country. This dataset now contains ~1.4 million records covering ~450 species between 1968 and 2011. It is updated every couple of decades.

This data is at 10 km resolution (_i.e._ was a bird present / breeding in a particular 10 km square?). More recent surveys have been conducted at much higher resolution (based upon 2 km tetrads) and now include ~20 million records covering 99.9% of the country.

Until recently this data was only available in [book form](https://www.bto.org/our-science/publications/bto-books-and-guides/bird-atlas-2007-11-breeding-and-wintering-birds), but the 10km resolution data is now [freely available online](https://app.bto.org/mapstore/StoreServlet). For any species you can view a map of the UK showing if and where it is present in the winter, and whether it possibly, probably or definitely breeds here in the summer.

{{< figure src="images/Screenshot-2019-05-20-19.07.31.png" caption="BTO atlas map" alt="" >}}

Inevitably, the maps are rather low resolution. You can just about see Ardnamurchan, but it's not obvious. The BTO also offer a variety of other ways to view the data, such as providing lists of birds by [searchable map reference or postcode](https://app.bto.org/birdtrack/servlet/BirdTrackAnonUserHandler?TargetURL=/grid-refs/grid-species-by-location.jsp).

## Local lists of local birds

Not only can you query the dataset interactively, you can also download the bird distribution data as compressed ZIP format comma-separated variable (CSV) text files. Uncompressed the files total about 125Mb. The largest is the geographic and temporal distribution data which runs to ~1.5 million lines. Don't try opening it in Excel (which is probably the default for this file type on your computer) as it can't cope with more than ~1 million rows [^433].
[^433]: Anyway, it doesn't make particularly interesting reading ... 

A wet spring weekend seemed like the ideal opportunity to generate an Ardnamurchan-specific bird list. CSV files are trivial to manipulate using a simple scripting language such as [perl](https://www.perl.org) or [python](https://www.python.org). What could possibly go wrong?

## 10 km resolution

Of those 1.5 million records, only a subset are relevant to Ardnamurchan. The rest of the country we can safely ignore.

The first challenge is to determine **which** 10 km squares overlay the ~30 km x ~10 km Ardnamurchan peninsula. The BTO uses the same grid overlay used by the Ordnance Survey and the latter provide a very useful [tile locator map](https://www.ordnancesurvey.co.uk/business-and-government/help-and-support/products/tile-locator-maps.html). If you select the relevant 100 km square (NM) you are taken to a more detailed view showing the individual labelled 10 km squares.

{{< figure src="images/Screenshot-2019-05-20-00.07.38.png" caption="Ardnamurchan 10 km map squares" alt="Ardnamurchan 10 km map squares" >}}

The numbering of these squares represent the first digits of the Eastings and Northings coordinates of the grid reference. For example, Acharacle primary school is at **NM** **6**74 **6**81 and is in the top right hand (north west) corner of NM66.

NM47, 57, 67, 46, 56, 66 covers Ardnamurchan in its entirety [^842], together with bits of Muck, Moidart and a small wedge of Morvern. That'll do.
[^842]: Defined at its eastern limit by the A861 Salen to Acharacle road.

## Big(ish) data

For the moment the only two data files that are of relevance are the lookup table of species (_species\_lookup.csv_) and their distribution (_distributions.csv_).

_species\_lookup.csv_ has four fields, the unique species code (an integer [^718]), the common and scientific name(s) and an indication whether it is a distinct species or an aggregate [^1345].
[^718]: Which includes 465 species from #1 (Red throated Diver - a resident breeding bird on Ardnamurchan) to #1663 (Blue-crowned Parakeet - unaccountably absent as I would think the habitat was perfect). Clearly the numbers are not sequential, presumably explained by the list containing a number of rarities, vagrants and escapees at the end derived from a much bigger list covering a larger geographic area.
[^1345]: For example, #475, the Common/Lesser Redpoll, _Acanthis flammea/cabaret_ is a species aggregate.

_distributions.csv_ has eight fields including the survey period, season, species (the id number only), 10 km reference square and whether breeding was possible, probable or confirmed. I've ignored the additional fields for the moment. With ~1.5 million lines in the file there are multiple records for each 10 km square and for each species.

{{< figure src="images/190506-066.jpg" caption="Siskin (male)" alt="Siskin (male)" >}}


For example, there are 2082 records for the six 10 km squares covering Ardnamurchan and 9290 records for the Barn Owl (_Tyto alba_) covering the entire country.

Of these, only seven intersect. The Barn Owl is present in five squares during the winter, but breeding is only suspected or known in NM67 and NM56.

This doesn't really qualify as 'big data' but untangling it is too much to handle with just a pen and paper [^705]. Instead, it's a trivial exercise to spend a wet afternoon (when I couldn't do any [beekeeping](https://www.theapiarist.org/)) writing some perl scripts to extract the relevant records for presentation.
[^705]: You want big data? The recent imaging of a black hole involved recording 5 petabytes of data by the [_Event Horizon Telescope_](https://eventhorizontelescope.org). That's equivalent to about 5000 years of MP3 music. So much data in fact that it was stored on half a ton of hard drives and transported by plane, rather than being transmitted over the network. That's big data!

## Data mangling and untangling

The historical information in the BTO Bird Atlas data is of less interest to me (at the moment at least [^484]). I'm interested in the most recent reports from the winter and breeding season records ... these are the birds I (and visitors to Ardnamurchan) are most likely to see now.
[^484]: And it is available on the BTO website if needed.

{{< figure src="images/181028-083.jpg" caption="Maclean's Nose" alt="Maclean's Nose" >}}

Following the usual cycle of code, debug, coffee, code, debug, pizza I had something that just about worked.

A total of 143 species overwinter, breed or both on Ardnamurchan. Of these, 26 (mostly overseas migrants like the cuckoo and willow warbler) are absent in winter. In contrast, 34 species are either absent in the summer or do not breed on Ardnamurchan.

Unsurprisingly considering the limited land area present in NM47 and NM57, these 10 km squares have the smallest number of summer or winter species:

- NM47 - winter 59, breeding 56
- NM57 - winter 49, breeding 48
- NM67 - winter 83, breeding 89
- NM46 - winter 66, breeding 89
- NM56 - winter 77, breeding 81
- NM66 - winter 103, breeding 90

It's worth noting here that presence alone in the summer is **not** recorded for any species on Ardnamurchan. Just because a particular species does not breed does not mean there is no chance of seeing it [^649]. For example, I've regularly seen gannets in Loch Sunart though they don't breed on the peninsula. 
[^649]: Within reason ... the Blue-crowned Parakeet is likely to be a no-show I'm afraid.

## Data presentation

Having sliced and diced the BTO data it now needed to be presented in a readable format.

Rather than just present a 'flat' list of birds it seemed logical to include links to relevant information online. For example, to the [BTO Bird Atlas maps](https://app.bto.org/mapstore/StoreServlet) of the entire UK for the winter and breeding season distributions and to the [BTO Bird Facts data](https://www.bto.org/understanding-birds/birdfacts/find-a-species).

This turned out to be a little bit more complicated than it should have been. The BTO appear to use two different numbering schemes.

Species in the BTO Bird Atlas use a taxonomically-organised sequentially-numbered list of UK species. I've mentioned the red throated diver (#1) and Blue-crowned Parakeet (#1663) previously. In contrast, the Bird Facts pages are referenced using the 5 digit [EURING code](https://app.bto.org/euringcodes/species.jsp) used by bird ringers. The EURING code for the Red throated diver is 00020 [^271].
[^271]: With leading zeros usually dropped when using the number.

Initial attempts to find the Blue-crowned Parakeet on the EURING list failed which highlighted a second problem [^239]. The scientific names (the only sort of names used) on the EURNG lists are sometimes different from the BTO lists. This happens when birds are reclassified. On the BTO the Blue-crowned Parakeet is _Thectocercus acuticaudatus_ whereas EURING lists it as _Aratinga acuticaudata_. D'oh!
[^239]: Please note that I wasn't really worried I'd somehow overlook this species in preparing the lists, or that if I did it would matter. The Blue-crowned Parakeet is the **last** record on the BTO UK species list in the _species\_lookup.csv_ file. Therefore, running the cross-referencing scripts returns it as the last line of the output. It's therefore easy to see. There are a others missing which **do** occur on Ardnamurchan.

{{< figure src="images/190201-017.jpg" caption="Winter snow on the Morvern hills - poor conditions for the Blue-crowned Parakeet" alt="Winter snow on the Morvern hills" >}}

I cross-referenced the two lists automagically using a short perl script and then manually corrected the dozen or so species from Ardnamurchan that disagreed between BTO and EURING systems [^283].
[^283]: These were a couple of ducks, black-headed gulls and a few finches like siskin, linnet, greenfinch.

Inevitably this manual bodge will break things in the future ...

## A picture is worth a thousand words

One of the problems with the [BTO Bird Atlas](https://app.bto.org/mapstore/StoreServlet) maps is that the Ardnamurchan peninsula is rather difficult to see. I therefore created a series of small 3x2 gridded icons representing the six NM-prefixed squares that cover the peninsula. I used one icon for the winter distribution and one for the breeding distribution (with probability indicated by different sized 'blobs', just as they are on the BTO Bird Atlas maps). For example:

This icon  ![](images/w101111.png "")  represents a species that is recorded in all but NM57 in winter.

This icon  ![](images/b032132.png "")  indicates a species which **possibly** breeds in NM46, **probably** breeds in NM66 and NM67 and that breeding has been **confirmed** in NM56 and NM57.

There are ~132 different distributions of birds in the winter and breeding seasons. Rather than draw any of the icons by hand I used [ImageMagick](https://www.imagemagick.org) to create them automagically, called from a perl script that read the underlying data directly from the _distributions.csv_ file.

I also added a **notes** column, but this has yet to be populated.

The finished list of Ardnamurchan birds in the most recent BTO census is linked from the menu above, or [directly from here](/birds/). It will be updated as and when new BTO census data is released.

* * *

## Notes

1. It should be noted that for security reasons the breeding distribution of some rare birds is deliberately listed (by the BTO) at lower resolution.
2. There's a second minor problem with the BTO Bird Atlas maps. They are displayed via a server which separates the delivery of the map from the menus that control the data displayed or its appearance. This means I could either link directly to the maps (and have no menus) or to link to the default map for a species and subsequently select the desired map (which has to be done interactively). The default map is the most recent breeding distribution, so this is linked from the 'summer' icons. Until I find a way to access the winter distributions **and** menus I've left the 'winter' icons linked directly to the relevant map alone.
3. The Blue-crowned Parakeet (_Thectocercus acuticaudatus_) is a small green South American parrot with a blue head. They inhabit Neotropical savanna-like habitats, woodland and forest margins from eastern Columbia to northern Argentina. Not Ardnamurchan :wink:

{{< figure src="images/Aratinga_acuticaudata_-San_Isidro_-Bolivia_-eating-8.jpg" caption="" alt="" >}}

