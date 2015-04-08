# circumventing-censorship
Simplify the editing and translation of Voice of America's ["Circumventing Censorship" project](http://projects.voanews.com/circumvention/).

VOA created a website promoting online tools to help people circumvent government attempts to restrict access to the internet. We want to republish that content as epubs that can be downloaded and shared. We also needed a way to simplify the addition and editing of meta data and translations. 

We're using the ePub3 format, which is basically a series of XHTML documents that are zipped together using a very specific structure. The idea of manually trying copy and paste the text into the appropriate tags throughout the book seemed tedious and destined for errors.

###How it works
I created an Express Node application that uses a Google spreadsheet to provide the data. [The spreadsheet](https://docs.google.com/spreadsheets/d/123DWrahipU6XOVjnVdTd0kdOBFBlzXuxButFymJ-OmA/pubhtml) has sheets for each tool as well as general translations. We shared the document with editors who can provide translations and corrections. 

I'm using [Tabletop.js](https://github.com/jsoma/tabletop) to simplify working with the published spreadsheet. I save the data to a series of JSON files. I use setInterval to periodically update the files with edits from the spreadsheets.

By using a single source for the data, I can ensure that changes to chapter titles are accurately reflected in the table of contents and the chapter itself. That images that appear in the book are listed in the required content.opf document. And that edits remain current.

###Downloading the ebooks.
I wrote a simple app for downloading and compiling the various components of each epub.
