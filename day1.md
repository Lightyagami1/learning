# Day 1 of Boot camp

* Hierarchy
vCentre >> Data centre >> Cluster/Host >> ESXi

* vCentre can be deployed 
 - directly
 - or on cluster

* Plural sight course on vCentre 5x (low priority task)

* no of ways to create vm in vSphere = 6

--- 
# VM Dev Tools

## git
 - git pull --rebase
 - search : a successfule git branching model
 - don't commit directly to main build ever :P

## Review Board
 - jira
  + add new feature
  + fix bugs

 - screw otheres on review board

---
## Build web
to build binaries in a common environment
* Sandbox build 
 - for testing
 - before check in

* Needed for 
 + environment for execution
 + code sanity
 + storing the data
 + dedicated resources required for testing
 + logs are generated for history

* changes are saved as a single file, not layer by layer as per new changes
* in modes, 
  + obj : to bring break points in code to limit the execution of code
  + beta
  + release

## Artifactory
 * to manage binaries shipping

## Toolchain
* internal to vmware to use while building 
* use external binaries that are needed for vmware products eg. gcc, perl, make etc
* all official binaries are available here
* search wiki vmware

## Tomcat

# Build tools
* Maven
* Gradle


### to compile java class
* jar file
## Maven
* Dependency tool for java

