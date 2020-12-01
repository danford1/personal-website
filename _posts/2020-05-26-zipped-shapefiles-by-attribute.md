---
title: Export Shapefiles by Attribute Name and Save Each to a Zip File
tags: [Mapping]
image: /assets/images/projects/project-inhabited-01.png
style: border
color: primary
description: Follow three steps to get a zipped shapefile of each field value in a spatial data set.
---

Social post:
Are you using software that requires zipped shapefiles for upload?

A method for splitting a shapefile into individual files based on an attribute value, and then zipping each shapefile based on its name.


## 1. Create and format shapefile

Have an attribute field on which you will base the separation.

## 2. Use tool in GIS software to zip base on Attribute

### ArcGIS Pro

### QGIS


## 3. Run script to zip each shapefile

This step is helpful if you need to upload shapefiles to a service that accepts zipped shapefiles. I'm using Landscape, a mobile data collection and property data management system for land conservation. We have Landscape set up with unique pages for each preserved property, including a map that show the protected area boundary.

``` python
#Author: Brian Greer - http://www.bgcarto.com/zip-all-shapefiles-in-directory-individually/

#directory of shapefiles to zip for zipping individual shapefiles

#import modules needed
import os
import glob
from zipfile import *

#define location of shapefiles and destination of zipped shapefiles
source = r"C:\Users\uname\folder"
dest = r"C:\Users\uname\folder\zip"

#change the current directory
os.chdir(source)

#test current directory
retval = os.getcwd()
print(retval)

#list all files with extension .shp
shps = glob.glob(source+"/*.shp")
print(shps)

# create empty list for zipfile names
ziplist = []

# create destination directory if it does not exist
if not os.path.exists(dest):
    os.makedirs(dest)

#populate ziplist list of unique shapefile root names by finding all files with .shp extension and removing extension
for name in shps:
  #prints full path for each shapefile
  print(name)
  #retrieves just the files name for each name in shps
  file = os.path.basename(name)
  #removes .shp extension
  names = file[:-4]
  #adds each shapefile name to ziplist list
  ziplist.append(names)

#prints ziplist to confirm shapefile root names have been added
print(ziplist)

#creates zipefiles in dest folder with basenames
for f in ziplist:
  # prints each itme in the ziplist
  print(f)
  #creates the name for each zipefile based on shapefile root names
  file_name = os.path.join(dest, f+".zip")
  #print to confirm
  print(file_name)
  #created the zipfiles with names defined above
  zips = ZipFile(file_name, "w")
  print(zips)
  #files lists all files with the current basename (f) from ziplist
  files = glob.glob(str(f)+".*")
  # iterate through each basename and add all shapefile components to the zipefile
  for s in files:
    print(s)
    zips.write(s)
  zips.close()
```

Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
