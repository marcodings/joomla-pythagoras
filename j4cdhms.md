# CDH Milestone

Showcase JoomlaX with basic **article** component __[1]__. The showcase is to  serve as the proof of concept 
for the JoomlaX (see note) architecture. The proof of concept is meant as an educational example,
to show the workings, discuss and build upon.
The core architecture is NOT imposed on anybody other than developers contributing to core. A compatibility layer is envisioned that will encapsulate/shield the core. The compatibility layer will ensure that extensions should not have to change and suffer BC in a major way. The compatibility layer is NOT part of the CDH. Ultimately we would encourage developers to migrate over but in this major version it is not a requirement.

The concept will cover 

* Universal content types
* Rendering 
* Storage
* Workflow
* Command bus
 
As a reference we use the basic architecture picture as shared previously
![Alt text](j4cdhms.png)

Do note that the repo is in an embryonic stage as of beginning og march and is in no way representative of the milestone result

## [2] Universal content types ( UCT )
Abstract/semantic definitions of content where UCT ultimately are combined into a Content Tree to be rendered by an arbitrary renderer outputting based on HTML, Json etc. The majority of UCT's will be defined by the UX working group. 
For CDH milestone purposes a limited number (2 to 4) of UCT's will be defined by ARCH to show the working of the renderer.  Any additional items available from UX team are considere a bonus

## [3] Renderer
Render the Content tree ( CT ) with a limited number of UCT's.

Output to plain HTML, without JS. The plain HTML renderer can serve as a base for
people with more JS skills. Or people with other requirements such as JSON, twig ....

## [4] Storage 
Storing content is handled a a two staged incremental development approach
### CSV based storage
Outset for experimenting and getting started
### "ORM" like storage
System glue to storage layer. doctrine dbal. The CQRS aspects are dealt with different Persistors and Lookup methods. These could facilitate different types of storages engines for read and write based upon the dbal.
 
## [5] Workflow
Workflow is choosen as an example for the horizontal component, showcasing the the different states being offered to "article vertical

* Published
* UnPublished
* Archived
* Trashed

The article component as vertical will "get" the horizontals functionality automatically. 

## [6] Channel independancy border
Make use of Chris Davenports [Service layer](https://github.com/chrisdavenport/service Service layer "Service layer")
Show
* API
* Joomla PHP

## Command bus
Will evolve to use Tactician ( or something else as we decided to use micro librairies ). Should showcase the interaction with the system as now is beeing handled by plugins

#NOTE

* Term like ORM are the best aproximation of inteded functionality, in this example ORM does not mean a full fledged ORM as we might know it.
* JoomlaX is used instead of Joomla4 because there might be a need to promote a member of the Joomla 3.x series to J4 because it may be desired to do so in light of backward compatibility break for php version, removal of depricated code or other.
