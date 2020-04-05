# Important-tips-about-module-import
Important !!!!
URL: https://stackoverflow.com/questions/13598958/import-modules-from-different-folders

#######################################################################################################################################
When I do this in Python 2.7 I use:                                                                               

import sys
sys.path.append('C:/python/files/folder1')

import a
import a1
UPDATE

Here's a hack I built to import all modules in a directory into a dictionary:

import os
import sys

dir_of_interest = 'C:/python/files/folder1'
modules = {}

sys.path.append(dir_of_interest)
for module in os.listdir(dir_of_interest):
    if '.py' in module and '.pyc' not in module:
        current = module.replace('.py', '')
        modules[current] = __import__(current)
I just built it and it's extremely hacky but it might be more like something you want. So, to access the module you want, instead of saying module_name.thing you would say modules["module_name"].thing
########################################################################################################################################
