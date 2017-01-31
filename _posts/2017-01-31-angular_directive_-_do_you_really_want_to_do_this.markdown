---
layout: post
title:  "Angular Directive - Do you really want to do this?"
date:   2017-01-31 03:09:25 +0000
---


During my final project application I implemented a really awesome angular directive that I think will be very useful to many new developers. ng-really? is an AngularJS directive that creates a confirmation dialog for an action. You are able to create a message that is asked when you ng-click or ng-submit in your appplication and if you confirm "yes" it will then run the function for ng-click or submit. I first used it to get confirmation when someone wanted to delete something. 

The implementation of it is very easy. Create the directive from the url and include the following code to run. 

This is an example from my project. I have a semantic ui x icon link to delete a Review in my application. When you click the link, it will ask you "Are you sure you want to delete?" If I select yes then my ng-really-click function will run, otherwise you can cancel and stop the action.

<i class="remove link icon" ng-really-message="Are you sure you want to delete?" ng-really-click="vm.deleteReview(review.id)"></i>

Below is the github link for the directive. I hope someone can find some use for it in their application. Let me know! 

https://gist.github.com/asafge/7430497
