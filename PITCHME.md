### Prototyping with the International Image Interoperability Framework (IIIF)  

Terry Brady

Georgetown University Library

https://github.com/terrywbrady/info

![](https://www.library.georgetown.edu/sites/default/files/library-logo.png)

+++

## IIIF: International Image Interoperability Framework

![IIIF Icon](https://upload.wikimedia.org/wikipedia/commons/e/e8/International_Image_Interoperability_Framework_logo.png)
* http://iiif.io

+++

## 4 API's

http://iiif.io/technical-details/

* Image API
* Presentation API
* Authentication API
* Search API

+++

## My Background

![Digital Georgetown Institutional Repository](https://repository.library.georgetown.edu/themes/ir//images/ir-logo.png)

* Lead developer for [DigitalGeorgetown](https://repository.library.georgetown.edu)
* DigitalGeorgetown showcases unique digital collections and digitized assets from the Georgetown University Library
* The IIIF Protocol promises to solve a number of challenges for our repository
* I am an enthusiastic user of IIIF - not a contributor to the standard

---

## What is needed to use IIIF?

* Images loaded into a IIIF compliant server
* Creation of a "manifest" to present these images
* Use of a IIIF compliant viewer
* The magic is in the interoperability of these tools

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

---

## Demo - Configuring an Image Server

+++

## Sample Images

https://raw.githubusercontent.com/terrywbrady/iiif-seajug/master/sample-images/lily1.jpg

https://raw.githubusercontent.com/terrywbrady/iiif-seajug/master/sample-images/lily2.jpg

https://raw.githubusercontent.com/terrywbrady/iiif-seajug/master/sample-images/lily3.jpg

+++ 
## IIIF Image Server

+++ 
## Load Image 1

* /iiif/2/lily1.jpg/info.json
* /iiif/2/lily1.jpg/full/full/0/default.jpg
* /iiif/2/lily1.jpg/full/full/10/default.jpg
* /iiif/2/lily1.jpg/800,300,800,800/full/10/default.jpg
* /iiif/2/lily1.jpg/800,300,800,800/200,200/0/default.jpg

+++

  