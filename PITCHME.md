### Prototyping with the International Image Interoperability Framework (IIIF)  

Terry Brady

Georgetown University Library

https://github.com/terrywbrady/info

![](https://www.library.georgetown.edu/sites/default/files/library-logo.png)

+++

## My Background - Georgetown

![Digital Georgetown Institutional Repository](https://repository.library.georgetown.edu/themes/ir//images/ir-logo.png)
* Applications Programmer Analyst for the Georgetown University Library
  * Lead developer for [DigitalGeorgetown](https://repository.library.georgetown.edu)
+++

## My Background - Prior to Georgetown
* LexisNexis: Metadata Management and Publishing Systems
* National Archives and Records Administration: Digitization Systems
* Developed software for corporations, non-profits, government and higher education
* Java developer since 1999

+++

## IIIF: International Image Interoperability Framework

![IIIF Icon](https://upload.wikimedia.org/wikipedia/commons/e/e8/International_Image_Interoperability_Framework_logo.png)
* [http://iiif.io](http://iiif.io)

+++

## 4 API's

http://iiif.io/technical-details/

* Image API
* Presentation API
* Authentication API
* Search API

+++

## Digital Georgetown and IIIF

* DigitalGeorgetown showcases unique digital collections and digitized assets from the Georgetown University Library
* The IIIF Protocol promises to solve a number of challenges for our repository
* We are enthusiastic users of IIIF - not a contributor to the standard

+++

## Digital Repository Challenges

* Provide low-resolution versions of images for low-bandwidth users
* Provide high-resolution versions of images for interested users
* Allow scholars to create citations to specific images or regions of images
* Simulating browsing of digitized manuscripts
* Provide visual navigation across a collection of items with no logical "pagination"
* Support the side by side comparison of historical objects

---

## What is needed to use IIIF?

* Images loaded into a IIIF compliant server
  * http://iiif.io/apps-demos/#image-servers
* Creation of a "manifest" to present these images
* Use of a IIIF compliant viewer
  * http://iiif.io/apps-demos/#image-viewing-clients
* The magic is in the *interoperability* of these tools

---

## IIIF Image API

* Map of Dublin (36 MB)
  * https://iiif.ucd.ie/loris/ucdlib:42220/full/full/0/default.jpg
  * 13401 x 9092
* IIIF Metadata for Image |
  * https://iiif.ucd.ie/loris/ucdlib:42220/info.json
+++

## IIIF Image API - Sampling

* Map of Dublin Region - Selected Region
  * https://iiif.ucd.ie/loris/ucdlib:42220/1182,2883,3039,2741/full/0/default.jpg
* Map of Dublin Scaled to 15% |
  * https://iiif.ucd.ie/loris/ucdlib:42220/full/pct:15/0/default.jpg

+++

## IIIF Image API - Resizing

* Map of Dublin Scaled to 800px Wide 
  * https://iiif.ucd.ie/loris/ucdlib:42220/full/800,/0/default.jpg
* Map of Dublin Scaled to 15% |
  * https://iiif.ucd.ie/loris/ucdlib:42220/full/pct:15/0/default.jpg

+++

## IIIF Image API - Rotation

* Map of Dublin Scaled to 15% and rotated 45 degrees
  * https://iiif.ucd.ie/loris/ucdlib:42220/full/pct:15/45/default.jpg

+++

## Stanford Image Cropping Tool for IIIF compliant images

* [Stanford Image Cropper](https://stanford.edu/~efisch17/iiif-tools/cropper/)
---

## IIIF Presentation API

http://iiif.io/api/presentation/2.1/

A collection of images can be assembled and documented in a "manifest".  

IIIF viewers render the contents of a manifest.

+++

## IIIF Manifest Editor

http://iiif.bodleian.ox.ac.uk/manifest-editor/#/?_k=ejb3xc

+++

## Sample Manifest

* https://github.com/terrywbrady/iiif-seajug/blob/master/manifests/UCDublin-Manifest.json
* https://raw.githubusercontent.com/terrywbrady/iiif-seajug/master/manifests/UCDublin-Manifest.json

---

## IIIF Viewers

Viewers with an awareness of the IIIF Standard

* http://iiif.io/apps-demos/#image-viewing-clients

+++

## Universal Viewer

* [Universal Viewer](http://universalviewer.io)
  * If you do not supply a manifest, it randomly finds one to show off
  * [Universal Viewer with Our Sample Manifest](http://universalviewer.io/uv.html?manifest=https://raw.githubusercontent.com/terrywbrady/iiif-seajug/master/manifests/UCDublin-Manifest.json)

+++

## Mirador

* [Mirador](http://projectmirador.org)
  * [Mirador Advanced Features](http://projectmirador.org/demo/advanced_features.htm)
  * Imagine 2 institutions with fragments of a historical artifact - the viewer can join them together l)
  
## Other Demos

http://iiif.io/apps-demos/#implementation-demos  
  
---

## Demo - Configuring an Image Server

* [Cantalope](https://medusa-project.github.io/cantaloupe/)
  * Java implementation of an image server
  * Quick an easy to configure
  
+++
  
## Cantaloupe - Location of Source Images

* Images are located with an "Image Resolver"
  * File System
  * Http Server 
  * JDBC
  * Amazon Storage
  * Azure Storage
* Configurable logic via the *delegate script* (Ruby)

+++ 

## Sample Images

* https://github.com/terrywbrady/iiif-seajug/tree/master/sample-images
* https://raw.githubusercontent.com/terrywbrady/iiif-seajug/master/sample-images/lily1.jpg
* https://raw.githubusercontent.com/terrywbrady/iiif-seajug/master/sample-images/lily2.jpg
* https://raw.githubusercontent.com/terrywbrady/iiif-seajug/master/sample-images/lily3.jpg

+++ 

## Demo Tasks
* Install Cantaloupe
* Configure Cantaloupe to use an HttpResolver pointing at my github repo
* Open server landing page
* Open an image
  * /iiif/2/lily1.jpg/info.json
  * /iiif/2/lily1.jpg/full/full/0/default.jpg
* Create a manifest
* View the manifest

---

## DigitalGeorgetown Use Cases for IIIF

* Manuscript Viewing
* High resolution image viewing
* View a collection of related images
* View a collection of related objects (images and documents)
* View a collection of related objects described in an archival system
  * Convert an [encoded archival description](https://www.loc.gov/ead/) into a manifest

+++

## Next Steps for DigitalGeorgetown

* Choose an image server
* Prototype a manifest builder to extract metadata from [DSpace](http://dspace.org)
* Prototype a manifest builder to extract metadata from [ArchivesSpace](http://archivesspace.org/)
* Determine how to deploy and manage manifest files
* Calculate cost of hosting high-resolution images for user access

---

## Even More IIIF Resources

* https://github.com/IIIF/awesome-iiif#tutorials

  