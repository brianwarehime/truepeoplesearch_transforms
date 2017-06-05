# truepeoplesearch_transforms
Maltego Local Transforms for truepeoplesearch.com

I just released some new local Maltego transforms for truepeoplesearch.com and wanted to go through some things about them in this post.

First, truepeoplesearch.com is a relatively newish site for getting some details about a person of interest. It also has some surprisingly great results about the person, so, if you haven't done so already, I would recommend you [request your records be removed](https://www.truepeoplesearch.com/removal).

I wanted to build some quick transforms that were able to extract all the data you can find on truepeoplesearch.com, so, with that, I built a transform set for Maltego that can currently grab:

- Current Address
- Previous Known Addresses
- Phone Number
- Email Addresses
- Possible Relatives
- Possible Known Associates
- Current/Past Places of Employment

Screenshot of sample results:

![](http://i.imgur.com/g3NO4nF.png)

A typical workflow looks something like this:

- A user uses my updated "Person" entity, which supports the new property field called "Address". It's basically the same entity, but, I just add a new property called Address to filter search results.
- You can either use it without an address supplied and get all locations returned, or, if you supply a location in the format of "City, State", will only return results from that location. *Although, this appears to not work as well as intended, may take some additional tweaking.
- When you run the "List Matches" transform, you will be given new Person entities, one for each match. These entities will contain a new property value called "URL", which contains the URL to their results.
- The new results will have the person's name, along with their location underneath, so you can attempt to narrow down your findings and get a better idea if it's the target you are interested in.
- From there, you have the whole suite of transforms to use on the new Person entity.

## Requirements
- You need to have `requests` and `BeautifulSoup` installed. Which can be done through `pip install requests` and `pip install beautifulsoup`

## Installation
- Grab the .mtz file I have hosted on my github, here.
- Import this .mtz file into Maltego, by going to the top-left icon, then Import, then Import Configuration.
- Grab the Python code from my Github for the transforms.
- Move the truepeoplesearch folder to `/opt/Maltego` *You'll most likely need to create this folder first

That should be all you need to get going, if you run into any issues or have bug reports/issues, please shoot them to me at brian@nullsecure.org, or on twitter @brian_warehime, or file an issue in Github.

Thanks!
