<div class="date"><b>overview</b></div>
	<div class="body">
	<p>varScoper is a cfc and corresponding views that are designed to identify variables created within a cffunction that don't have a corresponding (cfset var) statement.
<br><br>
If you have never missed a single (cfset var) statement when writing code, you can stop reading now.  If you don't know what (cfset var) is for, then you absolutely need to take a look at this code..</p><p>
</div>
<div class="date"><b>resources</b></div>
<div class="body">
If you are not quite sure why scoping variables within cffunctions is so important, you should take a look at the following resources. 
<br><br>
<a href="/web/20091119220726/http://ray.camdenfamily.com/downloads/cfcscopes.pdf">Raymond Camden's guide to variable scopes (pdf)</a></p><p>
Properly scoping variables is extremely critical especially as you start to cache cfc instances in shared scopes(session, application, server).  mach-ii and modelglue users should definitely be aware of this.</p><p></div>
<div class="date"><b>examples</b></div>
<div class="body">
The following is a link to a live example of varScoper.  It parses and identifies unscoped variables within a few of the popular open source ColdFusion frameworks.  You might be surprised with the results.
<br><br>
<a href="examples/varScoper.cfm">Link to varScoper example</a></p><p>
</div>
<div class="date"><b>features</b></div>
<div class="body">
Here are some of the things that varScoper will do</p><p><ul></p><p><li>Find unscoped variables created with a cfset within a cffunction</li>
   <li>Find unscoped variables created with cftags (cfloop, cfquery, etc)</li>
<li>Find unscoped variables and var statements within cfscript (excluding comments)</li>
   <li>Report line numbers of statements along with functions</li>
   <li>Link to a displayable copy of the file with line numbers</li>
   <li>Parse a single file, directory, or directory tree using absolute or relative paths</li>
   <li>Output to screen, or csv</li>
   <li>Fast and Lightweight: In my local environment (P4M 2.0, 2gbRAM, winXP), I processed 1126 files and 9030 cffunctions in 42594ms 
</ul>
varScoper currently supports the following tag:variable combos, please send me any additions.
<ul>
<li>cfloop:index
<li>cfloop:item
<li>cfquery:name
<li>cfinvoke:returnvariable
<li>cfdirectory:name
<li>cffile:variable
<li>cfparam:name
<li>cfsavecontent:variable
<li>cfform:name
<li>cfhttp:result### About (From Michaels site)
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
<li>cfquery:result<li>
cfimage:name<li>
cfmail:query<li>
cffeed:name<li>
cffeed:query<li>
cfftp:name<li>
cfwddx:output<li>
cfobject:name<li>
cfsearch:name<li>
cfprocresult:name<li>
cfpop:name<li>
cfregistry:name<li>
cfreport:name<li>
cfdbinfo:name<li>
cfdocument:name<li>
cfexecute:variable<li>
cfNtAuthenticate:result<li>
cfcollection:name<li>
cfpdf:name<li>
cfxml:variable<li>
cfzip:name<li>
cfldap:name</p><p></ul></p><p>
</div>
<div class="date"><b>known limitations</b></div>
<div class="body">
Here are some of the things that varScoper won't do
<ul>
   <li>Promise to find all unscoped variables: varScoper is a work in progress.  I've accounted for as many test cases as I can think of, but not all.  Please help by extending the testCaseCFC</li>
   <li>Display Line numbers for cfscript variables (It will tell you the function, but not the line number</li>
   <li>Ignore comments: (Fixed in 1.20) From what I can tell, I think I would need lookbehind within RegEx to do this.  CF RegEx doesn't support this, so I would need to use another implementation.  Any help on this would be appreciated.  (update: cfscript parsing is able to ignore comments )
</ul></p><p>DISCLAIMER: varScoper is only intended to identify POSSIBLE scoping problems within your code.  All code needs to be thoroughly analyzed to verify that a variable should be locally scoped within a function.</p><p>
</div>
