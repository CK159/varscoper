### About (From Michaels site)
varScoper is a cfc and corresponding views that are designed to identify variables created within a cffunction that don't have a corresponding (cfset var) statement.

If you have never missed a single (cfset var) statement when writing code, you can stop reading now.  If you don't know what (cfset var) is for, then you absolutely need to take a look at this code..

If you are not quite sure why scoping variables within cffunctions is so important, you should take a look at the following resources. 
[Raymond Camden's guide to variable scopes (pdf)](/http://ray.camdenfamily.com/downloads/cfcscopes.pdf/)

Properly scoping variables is extremely critical especially as you start to cache cfc instances in shared scopes(session, application, server).  mach-ii and modelglue users should definitely be aware of this.

### Features
Here are some of the things that varScoper will do;

* Find unscoped variables created with a cfset within a cffunction
* Find unscoped variables created with cftags (cfloop, cfquery, etc)
* Find unscoped variables and var statements within cfscript (excluding comments)
* Report line numbers of statements along with functions
* Link to a displayable copy of the file with line numbers
* Parse a single file, directory, or directory tree using absolute or relative paths
* Output to screen, or csv
* Fast and Lightweight: In my local environment (P4M 2.0, 2gbRAM, winXP), I processed 1126 files and 9030 cffunctions in 42594ms 

varScoper currently supports the following tag:variable combos, please send me any additions.
- cfloop:index
- cfloop:item
- cfquery:name
- cfinvoke:returnvariable
- cfdirectory:name
- cffile:variable
- cfparam:name
- cfsavecontent:variable
- cfform:name
- cfhttp:result
- cfquery:result
- cfimage:name
- cfmail:query
- cffeed:name
- cffeed:query
- cfftp:name
- cfwddx:output
- cfobject:name
- cfsearch:name
- cfprocresult:name
- cfpop:name
- cfregistry:name
- cfreport:name
- cfdbinfo:name
- cfdocument:name
- cfexecute:variable
- cfNtAuthenticate:result
- cfcollection:name
- cfpdf:name
- cfxml:variable
- cfzip:name
- cfldap:name

### Known Limitations

Here are some of the things that varScoper won't do
>Promise to find all unscoped variables: varScoper is a work in progress.  I've accounted for as many test cases as I can think of, but not all.  Please help by extending the testCaseCFC
* Display Line numbers for cfscript variables (It will tell you the function, but not the line number
* Ignore comments: (Fixed in 1.20) From what I can tell, I think I would need lookbehind within RegEx to do this.  CF RegEx doesn't support this, so I would need to use another implementation.  Any help on this would be appreciated.  (update: cfscript parsing is able to ignore comments )

### DISCLAIMER: 
varScoper is only intended to identify POSSIBLE scoping problems within your code.  All code needs to be thoroughly analyzed to verify that a variable should be locally scoped within a function.
