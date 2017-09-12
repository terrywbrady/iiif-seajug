# Cantaloupe Install Directory

Cantaloupe installation will go here. A couple of files will be overridden.

## Install (for demo)

- Run install.sh

## Uninstall (to repeat demo)

- Remove the install directory.
- In Codenvy, perform a Git->reset (hard)

## Codenvy Commands Pallette
If Cantaloupe is started from the Codenvy menu, then a preview URL will be generated that can access localhost:8182 from a public-facing URL.  
To enable this capability, configure the following Command.

### Name
Cantaloupe-3.3.2

### Commandline
java -Dcantaloupe.config=${current.project.path}/install/Cantaloupe-3.3.2/cantaloupe.properties -Xmx2g -jar ${current.project.path}/install/Cantaloupe-3.3.2/Cantaloupe-3.3.2.war

### Preview URL
http://${server.port.8182}/iiif/2/lily1.jpg/full/full/0/default.jpg