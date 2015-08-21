# TNA release process

Releases will be scheduled for once a week – maybe a Thursday or a Monday (we should discuss what is the ideal day for a release) – and changes will need to wait until the next release unless there is a very good reason not to.

Versions will be numbered major.minor.patch – 
```
e.g
                            0.3.1  
      major ---------------/ / /  
        minor --------------/ /  
          patch -------------/  
```
*Major* version numbers are when the complete code-base is affected – for instance, the intention is to bump the major from 0 to 1 when the code has been stripped of content and un-used files are removed from the theme and the theme is ready for open source.

*Minor* version numbers are when new features are added – this will normally happen at the end of a sprint if a release is planned.

*Patch* version numbers are for interim fixes and bug-fixes – this will be releases that happen mid sprint.

## Development process and release preparation: 
* You MUST pull before pushing
* All development MUST be done in ```feature/``` branches tracking ```develop```.
* ```feature/``` branches MUST ONLY be merged into ```develop``` when they are planned for the next scheduled release.
* All ```feature/``` branches MUST be pushed to Github at the end of the day so there is no risk of losing work in progress.
* When you merge a ```feature/``` branch into ```develop``` could you please note clearly in the commit description the following.
  * what the update does
  * what pages it affects
  * if it is reliant on any content/acf changes
  * any other important information
  * how the feature can be tested with success/fail criteria

## Release process:
Once a release has been confirmed:
* All features for the release MUST be pushed to Github (but ONLY features for release)
* A ```release/``` branch is created from ```develop``` - THIS WILL BE DONE BY WEBMASTER
* Designer/developers check out the ```release/``` branch
* Testing is done – editorial and webmaster, if possible will also do thorough testing of the ```release/``` branch on a development/testing machine
* Any last minute changes to the code are done on the ```release/``` branch – committed and pushed
* Once the ```release/``` branch is confirmed as ready
* the ```release/``` branch is merged into ```develop```
* the ```release/``` branch is merged into ```master```
* the ```release/``` branch is deleted
* a release is tagged from master – with a CHANGELOG and new version number - this should be done using Github's release process and must include information about all the features and fixes included in the release (which is why good commit commenting is essential)
* the release is deployed to DEVLB and, when confirmed, TESTLB and LIVELB
 
Once a release branch has been created features for the next release can start to be merged to develop.

### An example (based on fortnightly sprints):
* End of sprint 1
  * minor version release v0.3
* Start of sprint 2
  * patch release if required v0.3.1
* End of sprint 2
  * minor version release v0.4
* Start of sprint 3
  * etc.

## Branches
* ```master``` should ALWAYS match the LATEST release.
* ```develop```        should contain features/fixes for the NEXT release.
* ```feature/```      branches are taken off develop and are where all ongoing development happens.
* ```hotfix/```        branches are taken off master and are for URGENT fixes – this should be discussed with webmaster before.
* ```release/```      branches are taken off develop in preparing releases – small changes/bug-fixes can be made in the this branch if required

