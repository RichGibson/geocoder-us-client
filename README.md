geocoder-us-client
==================

A Node client library providing access to the features of http://geocoder.us 

Status: The Geocoder.us web service exists, and provides json resonses in a RESTful 
interface. This node module is in the 'Aspirational/Design' phase. I am describing 
and documenting the features which would make a node module more useful than simply 
using the API directly.


Geocoder::US is an open source Perl module written by Schuyler Erle which uses the US
Census TIGER data to geocode US addresses.

You pass in a US street address and get back a latitude and longitude.

Geocoder.us is a web site which has been offering free geocoding for low volumes and
non profits since May 2004. 

The site offers an API with several different interfaces. This node modules uses
the json interface.

Example of a call to Geocoder.us
http://rpc.geocoder.us/service/json?address=1600+Pennsylvania+Ave,+Washington+DC&parse_address=1

The results of that API call are:
[
   {
      "number" : "1600",
      "street" : "Pennsylvania",
      "lat" : "38.898748",
      "state" : "DC",
      "hash" : 1342946088,
      "zip" : "20502",
      "city" : "Washington",
      "suffix" : "NW",
      "long" : "-77.037684",
      "type" : "Ave",
      "prefix" : ""
   }
]

Note that the API call did not require you to have your address data in seperate variables 
for street, city,state, and zip.  Schuyler's original code does a lot of work on address 
standardization, and on breaking out the address componenets.

In the results you can see that you now have the address components broken out. Also note 
that geocoder.us returns an array of results. If you enter an ambiguous address, for 
example omitting 'North' on an address, you can get multiple returned addresses.

