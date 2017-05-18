# FlowViewer

This repository is a clone of the original FlowViewer 4.6 files from Sourceforge: 
[https://sourceforge.net/projects/flowviewer/](https://sourceforge.net/projects/flowviewer/)

**Version 4.6.1 Release Notes - 4 April 2017**

This release does not change any code of the original files, but factors them 
to make it easier to install in a Ubuntu docker instance.
(This avoids Steps 3-5 on page 4 of FlowViewer.pdf which are a pain...)

To use them, get the zip file from this github repository, unzip the package into /tmp,
and execute these commands (you may need sudo...):

```
curl https://github.com/richb-hanover/FlowViewer/archive/master.zip -0L > /tmp/FlowViewer-master.zip 
unzip /tmp/FlowViewer-master.zip -d /tmp
cd /var/www
sudo mv /tmp/FlowViewer/html/ .
sudo mv /tmp/FlowViewer/cgi-bin/ .
sudo chown -R www-data: html/
sudo find html -type f -exec chmod 664 {} + -o -type d -exec chmod 775 {} +
sudo chown -R www-data: cgi-bin
sudo chmod -R +x cgi-bin
```

The files will be in the proper directories (html & cgi-bin) with the proper permissions
