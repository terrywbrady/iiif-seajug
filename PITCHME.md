### Prototyping with the International Image Interoperability Framework (IIIF)  

Terry Brady

Georgetown University Library

https://github.com/terrywbrady/info

![](https://www.library.georgetown.edu/sites/default/files/library-logo.png)

---

### Overview
- About Me
- What is IIIF
  - Image API - Rendering Options
  - Presentation API - Presenting an image in context
- Demo: Configure a IIIF Image Server

---

### About Me

+++

### My Background - Georgetown

![Digital Georgetown Institutional Repository](https://repository.library.georgetown.edu/themes/ir//images/ir-logo.png)
- Software Developer for the Georgetown University Library
  - Lead developer for [DigitalGeorgetown](https://repository.library.georgetown.edu)
+++

### My Background - Prior to Georgetown
- LexisNexis: Metadata Management and Publishing Systems
- National Archives and Records Administration: Digitization Systems
- Developed software for corporations, non-profits, government and higher education
- Java developer since 1999


+++

### DigitalGeorgetown and IIIF

- DigitalGeorgetown showcases unique digital collections and digitized assets from the Georgetown University Library
- The IIIF framework promises to solve a number of challenges for our repository
- We are enthusiastic users of IIIF - not a contributor to the standard

+++

### Digital Repository Challenges

- Provide low-resolution versions of images for low-bandwidth users |
- Provide high-resolution versions of images for interested users |
- Allow scholars to create citations to specific images or regions of images |
- Simulating browsing of digitized manuscripts |
- Provide visual navigation across a collection of items with no logical "pagination" |
- Support the side by side comparison of historical objects |

---

### IIIF: International Image Interoperability Framework

![IIIF Icon](https://upload.wikimedia.org/wikipedia/commons/e/e8/International_Image_Interoperability_Framework_logo.png)
- Founded 2011
- [About IIIF](http://iiif.io/about/)

+++

### 4 API's

[http://iiif.io/technical-details/](http://iiif.io/technical-details/)

- Image API
- Presentation API
- Authentication API
- Search API

---

### What is needed to use IIIF?

- Images are made accessible to a [IIIF compliant server](http://iiif.io/apps-demos/#image-servers)
- Creation of a "manifest" to present these images
- Use of a [IIIF compliant viewer](http://iiif.io/apps-demos/#image-viewing-clients)
- The magic is in the *interoperability* of these tools


---

### IIIF Image API

- Provides a rich set of options to retrieve an image
  - Whole image or pixel coordinates
  - Image Scaling
  - Image Rotation
- These options are provided by the URL

+++

### Components of an IIIF Image URL

/ResourcePath/Region/Size/Rotation/Quality.Format

+++

### Resource Path

/**ResourcePath**/Region/Size/Rotation/Quality.Format

- Path to an image within an image server

+++

### Region
/ResourcePath/**Region**/Size/Rotation/Quality.Format

- "full"
- x,y,w,h
  - x,y pixel coordinates
  - w,h width and height
- other options exist

+++

### Size
/ResourcePath/Region/**Size**/Rotation/Quality.Format

- "full" or "max"
- w,
  - scaled to specific width
- ,h
  - scaled to specific height
- pct:n
  - scaled to specific percent
+++

### Rotation
/ResourcePath/Region/Size/**Rotation**/Quality.Format

- 0-360 (rotated)
- !0-360 (mirrored and rotated)

+++

### Quality
/ResourcePath/Region/Size/Rotation/**Quality**.Format

- "color"
- "gray"
- "bitonal"
- "default" - default value for a server

+++

### Format
/ResourcePath/Region/Size/Rotation/Quality.**Format**

- jpg
- png
- jp2
- tif
- other formats

+++

### IIIF Metadata

A IIIF Server returns a JSON description of a resource

- /ResourcePath/info.json
- Technical details about the image
- Feature support within the server

+++

### Sample IIIF Image: Map of Dublin
- ucdlib:42220/**info.json**
- [https://iiif.ucd.ie/loris/ucdlib:42220/info.json](https://iiif.ucd.ie/loris/ucdlib:42220/info.json)
  - 13401 x 9092 

_Resource is courtesy of University College Dublin_
 
+++

### Retrieving the full image
- Map of Dublin (36 MB) 
  - ucdlib:42220/**full/full/0/default.jpg**
  - [https://iiif.ucd.ie/loris/ucdlib:42220/full/full/0/default.jpg](https://iiif.ucd.ie/loris/ucdlib:42220/full/full/0/default.jpg)
  - 36 MB
   - This will be slow to load
  - Note the "Castle" within the image

_Resource is courtesy of University College Dublin_
 
+++

### Sampling a Region from the Image (the "Castle")
  - ucdlib:42220/**1182,2883,3039,2741**/full/0/default.jpg
  - [https://iiif.ucd.ie/loris/ucdlib:42220/1182,2883,3039,2741/full/0/default.jpg](https://iiif.ucd.ie/loris/ucdlib:42220/1182,2883,3039,2741/full/0/default.jpg) 

_Resource is courtesy of University College Dublin_

+++

### Retrieving a Scaled Image of the Full Map
- Map of Dublin Scaled to 800px Wide 
  - ucdlib:42220/full/**800,**/0/default.jpg
  - [https://iiif.ucd.ie/loris/ucdlib:42220/full/800,/0/default.jpg](https://iiif.ucd.ie/loris/ucdlib:42220/full/800,/0/default.jpg)
- Map of Dublin Scaled to 15% |
  - ucdlib:42220/full/**pct:15**/0/default.jpg
  - [https://iiif.ucd.ie/loris/ucdlib:42220/full/pct:15/0/default.jpg](https://iiif.ucd.ie/loris/ucdlib:42220/full/pct:15/0/default.jpg)

_Resource is courtesy of University College Dublin_

+++

### Map: Scaled and Rotated

- Map of Dublin Scaled to 15% and rotated 45 degrees
  - ucdlib:42220/full/pct:15/**45**/default.jpg
  - [https://iiif.ucd.ie/loris/ucdlib:42220/full/pct:15/45/default.jpg](https://iiif.ucd.ie/loris/ucdlib:42220/full/pct:15/45/default.jpg)

_Resource is courtesy of University College Dublin_

+++

### Image API is Useful

What can we do with this API? 

+++

### What can we do with this Image API?

- We will look at the IIIF Presentation API
- View our image in a IIIF Compliant Viewer

---

### IIIF Presentation API

[IIIF Presentation API](http://iiif.io/api/presentation/2.1/)

A collection of images can be assembled and documented in a "manifest".  

IIIF viewers render the contents of a manifest.

+++

### IIIF Presentation Terminology

- Manifest 
  - describes what is being presented such as a picture or a book 
- Sequence |
   - describes a sequence of images to present 
   - can support multiple navigation schemes
- Canvas |
   - the image to present 
- Advanced Features |
  - Layer (image overlays, annotations)
  - Collection (present a group of manifests)

+++

### Sample Manifest File

- [https://github.com/terrywbrady/iiif-seajug/blob/master/manifests/UCDublin-Manifest.json](https://github.com/terrywbrady/iiif-seajug/blob/master/manifests/UCDublin-Manifest.json)

+++?code=https://raw.githubusercontent.com/terrywbrady/iiif-seajug/master/manifests/UCDublin-Manifest.json
@[5,7,9](Custom metadata for this presentation)
@[24-26](Image Label and Size)
@[34](Path to Image Resource)


---

### IIIF Viewers

Viewers with an awareness of the IIIF Standard

- [Image Viewing Clients](http://iiif.io/apps-demos/#image-viewing-clients)

+++

### Universal Viewer

- [Universal Viewer](http://universalviewer.io)
  - If you do not supply a manifest, it randomly finds one to show off
  - [Universal Viewer with Our Sample Manifest](http://universalviewer.io/uv.html?manifest=https://raw.githubusercontent.com/terrywbrady/iiif-seajug/master/manifests/UCDublin-Manifest.json)

+++

### Mirador

- [Mirador](http://projectmirador.org)
  - [Mirador Advanced Features](http://projectmirador.org/demo/advanced_features.html)
  - Imagine 2 institutions with fragments of a historical artifact - the viewer can join them together)

---
  
### Other Demos

[IIIF Demos](http://iiif.io/apps-demos/#implementation-demos) 
  
---

### Demo - Configuring an Image Server

- [Cantalope](https://medusa-project.github.io/cantaloupe/)
  - Java implementation of an image server
  - Quick an easy to configure
  
+++
  
### Cantaloupe - Location of Source Images

- Images are located with an "Image Resolver"
  - File System
  - Http Server 
  - JDBC
  - Amazon Storage
  - Azure Storage
- Configurable logic via the *delegate script* (Ruby)

+++ 

### Sample Images

- [https://github.com/terrywbrady/iiif-seajug/tree/master/sample-images](https://github.com/terrywbrady/iiif-seajug/tree/master/sample-images)

![lily1.jpg](https://raw.githubusercontent.com/terrywbrady/iiif-seajug/master/sample-images/lily1.jpg) <!-- .element: style="width: 25%" -->
![lily2.jpg](https://raw.githubusercontent.com/terrywbrady/iiif-seajug/master/sample-images/lily2.jpg) <!-- .element: style="width: 25%" -->
![lily3.jpg](https://raw.githubusercontent.com/terrywbrady/iiif-seajug/master/sample-images/lily3.jpg) <!-- .element: style="width: 25%" -->

+++ 

### Demo: Install Cantaloupe

+++?code=https://raw.githubusercontent.com/terrywbrady/iiif-seajug/master/install/install.sh

+++?code=https://raw.githubusercontent.com/terrywbrady/iiif-seajug/master/install/run.sh

+++

### Server Config

- File resolver is configured for Codenvy
- Admin page is enabled.

+++?code=https://raw.githubusercontent.com/terrywbrady/iiif-seajug/master/install/Cantaloupe-3.3.2/cantaloupe.properties
@[110](FilesystemResolver enabled)
@[130](FilesystemResolver set for Codenvy)

+++

### Demo: Configure Cantaloupe to use an HttpResolver pointing at my github repo
- Open /admin link
- Set resolver to HttpResolver
- Set resolver prefix
```
  https://raw.githubusercontent.com/terrywbrady/iiif-seajug/master/sample-images/
```

+++

### Open Demo Image
  - /iiif/2/lily1.jpg/full/full/0/default.jpg
  - /iiif/2/lily1.jpg/full/full/0/gray.jpg

+++

### Stanford Image Cropping Tool for IIIF compliant images

- [Stanford Image Cropper](https://stanford.edu/~efisch17/iiif-tools/cropper/)
  - Sample image to crop

+++

### IIIF Manifest Editor

- [Manifiest Editor from Oxford University](http://iiif.bodleian.ox.ac.uk/manifest-editor/#/?_k=ejb3xc)
- Sample Manifest Source
```
  https://raw.githubusercontent.com/terrywbrady/iiif-seajug/master/manifests/UCDublin-Manifest.json
```

+++

### IIIF Manifest - Create a New Manifest

- /iiif/2/lily1.jpg/info.json
- /iiif/2/lily2.jpg/info.json
- /iiif/2/lily3.jpg/info.json

+++

### Save the manifest

https://github.com/terrywbrady/iiif-seajug/blob/master/manifests/lily-manifest.json

_The links in this manifest will change with each new Codenvy session_

+++

### Open Manifest with Universal Viewer

http://universalviewer.io/uv.html?manifest=https://raw.githubusercontent.com/terrywbrady/iiif-seajug/master/manifests/lily-manifest.json

---

### DigitalGeorgetown Use Cases for IIIF

- Manuscript Viewing |
- High resolution image viewing |
- View a collection of related images |
- View a collection of related objects (images and documents) |
- View a collection of related objects described in an archival system |
  - Convert an [encoded archival description](https://www.loc.gov/ead/) into a manifest

+++

### Next Steps for DigitalGeorgetown

- Choose an image server |
- Determine where to host high-resolution images |
- Prototype a manifest builder to extract metadata from Digital Repository |
- Prototype a manifest builder to extract metadata from Archival Repository |
- Determine how to deploy and manage manifest files |
- Calculate cost of hosting high-resolution images for user access |

---

### Even More IIIF Resources

- [List of Awesome IIIF Resources](https://github.com/IIIF/awesome-iiif#tutorials)

---

### Thank You!  

Terry Brady

Georgetown University Library

https://github.com/terrywbrady/info

![](https://www.library.georgetown.edu/sites/default/files/library-logo.png)
