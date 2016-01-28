# VarScoper (fork) 
This is a fork of Mike Schierberl's original VarScoper which hasn't been updated since 2010.  His main project site doesn't appear to be available, so I've captured that through archive.org and put most of it [Here](https://github.com/wiggick/varscoper/blob/master/about.md).  

New Features:
  - Updated for latest tags (CF11)
  - Added option to show corrected code in a textarea for easier copying.
  - Added option to apply padded tabs as a prefix
  - Added Corrected Code Style to suppord Tag vs CFScript.

### Version
1.4

### Installation Instructions:
Extract all files to a publicly accesible directory on your CFMX 6 or 7 server.  

Navigate to index.cfm or varscoper.cfm and enter the absolute or relative path to the template or directory that you would like to check. 

### History
    -v1.4
         - Updated for latest tags (CF11)
        - Added option to show corrected code in a textarea for easier copying.
        - Added option to apply padded tabs as a prefix
        - Added Corrected Code Style to suppord Tag vs CFScript.
    - v1.3
        - CF Builder Extension Support
        - Recognizes var statements anywhere in a function (CF9)
        - Issues (13,14,15,16,17,18,19,20,21,23,25,26,27,28,30,31,32) Fixed
        - Open BD/Railo Supported
        - CFScript comments parsed correctly
    - v1.2
		-Significant improvements to cfscript parsing engine
		-Issues (6,7,8,9,10,11) fixed
		-Ability to exclude files/folders using properties.xml (only when parsing a folder)
		-Ability to identify tags with "multiple personalities" i.e. cffeed/cfprocparam that can have different behaviors for output variables based on params
		-More agressive var scope checking (newly identified scenarios that were missed before)
		-Addition of unit testing suite
	-v1.12
		-added new tags to the parsing engine
		-added XML output support
		-fixed some bugs related to directory parsing in CF6
	-v1.1
		-added support for cfscript
	-v1.0
		-initial release
		-cf tag support
		-Find unscoped variables created with a cfset within a cffunction
		-Find unscoped variables created with cftags (cfloop, cfquery, etc)
		-Report line numbers and link directly to the line in the file
		-Output to screen or csv


### Features:
	-Identifies unscoped variables within cffunctions
	-can return line numbers of functions/variables

### Known Limitations:
	
	-(fixed 1.13) Returns false positive when variables are set within a comments block 
	-(fixed 1.13) If you don't scope an argument value, and then reference that value it 
	 will "technically" return a false positive...
		<cfargument name="foo">
		<cfset foo.foo2 = bar /> 
	instead of...
		<cfset arguments.foo.foo2 />

### Future TODOs:
	-(fixed 1.13) create a library of all cf tags that can create variables
	-(fixed 1.13) cfscript
	-(fixed 1.13) ignore things in comments (May need to use lookbehind?  Not supported in CF as far as I know)
	-Integration with cfeclipse
### LICENSE 
Copyright 2006 Mike Schierberl
Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at
http://www.apache.org/licenses/LICENSE-2.0
Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.
varScoper
