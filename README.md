Solr-install
============

A number of shell scripts to download, customize and install apache solr for use with Drupal 7 and the module search_api_solr.

The scripts will install the following:

  * [Apache Solr](http://lucene.apache.org/solr/) 3.x version using the included Jetty Servlet Container.
  * Copies the [search_api_solr](http://drupal.org/project/search_api_solr) configuration files into the solr instance.
  * Creates multicore instances tst, acc and prd.
  * Installs the software in /var/solr and a /etc/init.d/solr startup script
  * Runs the solr server


Installation
------------

I suppose we can assume you have git installed:

    $ git clone git://github.com/fjmk/solr-install.git
    $ cd solr-install
    $ sudo ./install-solr

You can test your installation: http://[yourhostname]/solr/tst/admin (change **tst** if you changed the core_names in the script)

For the Drupal configuration the Solr server URI is: http://[yourhostname]/solr/tst 


Customizing
-----------

The file create_solr starts with the lines: 

    #!/bin/bash

    # change the core names to your liking
    core_names="tst acc prd"

    # change to new versions if needed
    apache_solr_version="3.6.2"
    search_api_solr_version="7.x-1.0-rc3"

You can add/change core names here: (tst acc prd)  
3.6.2 is the current apache-solr version (3.x version)  
Change search_api_solr_version when there is a new verion on [drupal.org](http://drupal.org/project/search_api_solr)

License
-------

Copyright (C) 2011 [Frans Kuipers](http://franskuipers.nl/)  

This program is free software; you can redistribute it and/or modify it  
under the terms of the GNU General Public License, version 2, as published  
by the [Free Software Foundation](http://www.gnu.org/licenses/old-licenses/gpl-2.0.html).
