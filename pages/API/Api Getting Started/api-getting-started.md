---
title: Getting Started
keywords: API, REST, XMLRPC, Web-Services, Hub
last_updated: August 29, 2017
tags: 
summary: "An introduction to CrossKnowledge API."
sidebar: home_sidebar
permalink: api_getting_started.html
folder: API Getting Started
---

This document provides all the basic information you need to start using the CrossKnowledge API. It covers CrossKnowledge API concepts, shows examples for various use cases, and gives links to more information.

{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-thumbs-o-up fa-stack-1x fa-inverse'></i></span>&nbsp;Get an [access to the CrossKnowledge platform]( http://page.crossknowledge.com/contact-EN.html) to get started with the CrossKnowledge API." type="info" %}

## Overview

The CrossKnowledge API offers to our clients, partners or independant software vendors, a powerful way to create innovative learning application or to integrate with HRIS platform or any third party application.

<div class="alert alert-warning" role="alert">
    <i class="fa fa-exclamation-triangle"></i> API requests are limited to 500 requests every 60 seconds.
</div>

The CrossKnowledge API includes :

<script>

	$("#toc").hide();

</script>
<div class="row">

         <div class="col-md-3 col-sm-6">
             <div class="panel panel-default text-center">
                 <div class="panel-heading">
                     <span class="fa-stack fa-5x">
                           <i class="fa fa-circle fa-stack-2x text-info"></i>
                           <i class="fa fa-lock fa-stack-1x fa-inverse"></i>
                     </span>
                 </div>
                 <div class="panel-body">
                     <h4 id="api-auth">Authentication & Authorization workflow</h4>
                     <p>Access to the CrossKnowledge Learner API using the CKAuth authentication workflow.</p>
                     <a href="ckauth_workflow.html" class="btn btn-primary">Learn More</a>
                 </div>
             </div>
         </div>
         <div class="col-md-3 col-sm-6">
             <div class="panel panel-default text-center">
                 <div class="panel-heading">
                     <span class="fa-stack fa-5x">
                           <i class="fa fa-circle fa-stack-2x text-info"></i>
						   <i style="position:absolute; left:47px; top: 38px;" class="fa fa-user fa-stack-3x fa-inverse"></i>
                           <i style="left:-20px; top: -24px; font-size: 40px" class="fa fa-database fa-stack-1x fa-inverse"></i>
                           
                     </span>
                 </div>
                 <div class="panel-body">
                     <h4 id="online-api">Learner API</h4>
                     <p>Get data on behalf of the authorized user using CKAuth authentication workflow.</p>
                     <a href="api_web_services_list_and_details.html" class="btn btn-primary">Learn More</a>
                 </div>
             </div>
         </div>
         <div class="col-md-3 col-sm-6">
             <div class="panel panel-default text-center">
                 <div class="panel-heading">
                     <span class="fa-stack fa-5x">
                           <i class="fa fa-circle fa-stack-2x text-info"></i>
						   <i class="fa fa-database fa-stack-1x fa-inverse"></i>
						   
						   
                     </span>
                 </div>
                 <div class="panel-body">
                     <h4 id="offline-api">Administration API</h4>
                     <p>Get data out of a user context using simple API Key authentication.</p>
                     <a href="api_web_services_list_and_details_admins.html" class="btn btn-primary">Learn More</a>
                 </div>
             </div>
         </div>
		 <div class="col-md-3 col-sm-6">
             <div class="panel panel-default text-center">
                 <div class="panel-heading">
                     <span class="fa-stack fa-5x">
                           <i class="fa fa-circle fa-stack-2x text-info"></i>
                           <i class="fa fa-exchange fa-stack-1x fa-inverse"></i>
                     </span>
                 </div>
                 <div class="panel-body">
                     <h4 id="ckhub">Data Exchange Interfaces</h4>
                     <p>Integrate systems using flat files data exchange.</p>
                     <a href="#ckhub" class="btn btn-primary">Learn More</a>
                 </div>
             </div>
         </div>

</div>

## Authentication & Authorization workflow
The CrossKnowledge Authentication Service grants access to client application so they can access private data on behalf of the authenticated learner.
{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-graduation-cap fa-stack-1x fa-inverse'></i></span>&nbsp;Learn [how CrossKnowledge Authentication Service works.](/ckauth_workflow.html)" type="info" %}



## Learner API

The web-services included in our Learner API enable third party application to get the data from the CrossKnowledge Learning Suite on behalf the authenticated user. The returned data are contextualized to the learner logged during the web-service call out.

{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-lightbulb-o fa-stack-1x fa-inverse'></i></span>&nbsp;Thoses web-services can be used to enable the learner to access to their learning resources from their mobile devices." type="success" %}

Below is and exhaustive list of the web-services ordered by [CrossKnowledge Database Object](/glossary.html):

<ul id="profileTabs" class="nav nav-tabs">
	<li class="active" ><a href="#learner" data-toggle="tab">Learner</a></li>
    <li><a href="#trainings" data-toggle="tab">Training</a></li>
    <li><a href="#trainingSessions" data-toggle="tab">Training Sessions</a></li>
	<li><a href="#learningObject" data-toggle="tab">Learning Object</a></li>
    <li><a href="#tracking" data-toggle="tab">Tracking</a></li>
	<li><a href="#discussion" data-toggle="tab">Discussion</a></li>
	<!--<li><a href="#search" data-toggle="tab">Search Filters</a></li>-->
</ul>
  <div class="tab-content">
	<div role="tabpanel" class="tab-pane active" id="learner">
		<div class="panel-group" id="accordion0">
                    <div class="panel panel-default">
                        <div class="panel-heading">
                            <h4 class="panel-title" id="
lorem-ipsum-dolor-sit-amet-consectetur-adipiscing-elit
">
                                <a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion" href="#collapseOne" aria-expanded="false">/Learner/profile/get</a>
                            <a   style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
                        </div>
                        <div id="collapseOne" class="panel-collapse collapse noCrossRef" aria-expanded="false">
                            <div class="panel-body">
                                <h4>Description:</h4>
								<p>This web-service enables a third party application to get  (read) the current authenticated learner profile information.<a href="/api_web_services_list_and_details.html#learner_profile_get">Click here to see how it works.</a></p>
								</div>
                        </div>
                    </div>
                    <!-- /.panel -->
                    <div class="panel panel-default">
                        <div class="panel-heading">
                            <h4 class="panel-title" id="
curabitur-eget-leo-at-velit-imperdiet-varius-in-eu-ipsum-vitae">
                                <a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion" href="#collapseTwo" aria-expanded="false">/Learner/manager/get</a>
                            <a  style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
                        </div>
                        <div id="collapseTwo" class="panel-collapse collapse noCrossRef" aria-expanded="false">
                             <div class="panel-body">
							 <h4>Description:</h4>
								<p>This web-service enables a third party application to get (read) the current authenticated learner's manager profile information.<a href="/api_web_services_list_and_details.html#learner_manager_get">Click here to see how it works.</a></p>
								</div></div>
                        
                    </div>
                    <!-- /.panel -->
                    <div class="panel panel-default">
                        <div class="panel-heading">
                            <h4 class="panel-title" id="
aenean-consequat-lorem-ut-felis-ullamcorper
">
                                <a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion" href="#collapseThree" aria-expanded="false">/Learner/subordonates/get</a>
                            <a  style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
                        </div>
                        <div id="collapseThree" class="panel-collapse collapse noCrossRef" aria-expanded="false">
                                                          <div class="panel-body">

							 <h4>Description:</h4>
								<p>This web-service enables a third party application to get (read) the current authenticated learner subordonates profile information.<a href="/api_web_services_list_and_details.html#learner_subordinates_get">Click here to see how it works.</a></p>
								</div></div>
                        </div>
                    </div>

                    <!-- /.panel
                    <div class="panel panel-default">
                        <div class="panel-heading">
                            <h4 class="panel-title" id="
curabitur-eget-leo-at-velit-imperdiet-varius-in-eu-ipsum-vitae-1">
                                <a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion" href="#collapseFive" aria-expanded="false">/Learner/instanceParams/get</a>
                            <a   style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
                        </div>
                        <div id="collapseFive" class="panel-collapse collapse" aria-expanded="false">
                            <div class="panel-body">
<h4>Description:</h4>
								<p>This web-service enables a third party application to get (read) the current authenticated learner instance custom parameters.<a href="/api_web_services_list_and_details.html#learner_instance_param_get">Click here to see how it works.</a></p>
								                            </div>
                        </div>
                    </div>
                    
                    <!-- /.panel -->
</div>


	<div role="tabpanel" class="tab-pane" id="trainings">
	
	
		<div class="panel-group" id="accordion1">
                    <div class="panel panel-default">
                        <div class="panel-heading">
                            <h4 class="panel-title" id="
lorem-ipsum-dolor-sit-amet-consectetur-adipiscing-elit
">
                                <a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion1" href="#collapse1" aria-expanded="false">/Training/get</a>
                            <a   style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
                        </div>
                        <div id="collapse1" class="panel-collapse collapse noCrossRef" aria-expanded="false">
                            <div class="panel-body">
                                <h4>Description:</h4>
								<p>This web-service enables a third party application to get (read) the training in which the current authenticated learner is enrolled.<a href="/api_web_services_list_and_details.html#learner_trainings_get">Click here to see how it works.</a></p>
								</div>
                        </div>
                    </div>
					<div class="panel panel-default">
                        <div class="panel-heading">
                            <h4 class="panel-title" id="
lorem-ipsum-dolor-sit-amet-consectetur-adipiscing-elit
">
                                <a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion1" href="#collapse2" aria-expanded="false">/Search/get</a>
                            <a   style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
                        </div>
                        <div id="collapse2" class="panel-collapse collapse noCrossRef" aria-expanded="false">
                            <div class="panel-body">
                                <h4>Description:</h4>
								<p>This web-service enables a third party application to search a training available for the current authenticated learner.<a href="/api_web_services_list_and_details.html#learner_training_get">Click here to see how it works.</a></p>
								</div>
                        </div>
                    </div>
                    
	
	
	</div>
	</div>
	<div role="tabpanel" class="tab-pane" id="trainingSessions">
		
		
		
		
		
		
		<div class="panel-group" id="accordion2">
		
                    <div class="panel panel-default">
                        <div class="panel-heading">
                            <h4 class="panel-title" id="
lorem-ipsum-dolor-sit-amet-consectetur-adipiscing-elit
">
                                <a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion2" href="#collapse3" aria-expanded="false">/TrainingSession/get</a>
                            <a   style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
                        </div>
                        <div id="collapse3" class="panel-collapse collapse noCrossRef" aria-expanded="false">
                            <div class="panel-body">
                                <h4>Description:</h4>
								<p>This web-service enables a third party application to get (read) the training Sessions in which the current authenticated learner is enrolled.<a href="/api_web_services_list_and_details.html#learner_training_sessions_get">Click here to see how it works.</a></p>
								</div>
                        </div>
                    </div>
                   <div class="panel panel-default">
                        <div class="panel-heading">
                            <h4 class="panel-title" id="
lorem-ipsum-dolor-sit-amet-consectetur-adipiscing-elit
">
                                <a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion2" href="#collapse4" aria-expanded="false">/PathSessionFolder/get</a>
                            <a style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
                        </div>
                        <div id="collapse4" class="panel-collapse collapse noCrossRef" aria-expanded="false">
                            <div class="panel-body">
                                <h4>Description:</h4>
								<p>This web-service enables a third party application to get (read) the Sessions folder hierarchy for the current authenticated learner.<a href="/api_web_services_list_and_details.html#learner_path_session_folders_get">Click here to see how it works.</a></p>
								</div>
                        </div>
                    </div>
					
					
	</div>
	</div>
	<div role="tabpanel" class="tab-pane" id="learningObject">
		
		
		<div class="panel-group" id="accordion3">
                    <div class="panel panel-default">
                        <div class="panel-heading">
                            <h4 class="panel-title" id="
lorem-ipsum-dolor-sit-amet-consectetur-adipiscing-elit
">
                                <a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion3" href="#collapse5" aria-expanded="false">/LearningObjects/get</a>
                            <a   style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
                        </div>
                        <div id="collapse5" class="panel-collapse collapse noCrossRef" aria-expanded="false">
                            <div class="panel-body">
                                <h4>Description:</h4>
								<p>This web-service enables a third party application to get (read) the learning objects available for the current authenticated learner.<a href="/api_web_services_list_and_details.html#learner_learning_objects_get">Click here to see how it works.</a></p>
								</div>
                        </div>
                    </div>
                    <!-- /.panel -->
                    <div class="panel panel-default">
                        <div class="panel-heading">
                            <h4 class="panel-title" id="
curabitur-eget-leo-at-velit-imperdiet-varius-in-eu-ipsum-vitae">
                                <a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion3" href="#collapse6" aria-expanded="false">/LearningObjects/item/get</a>
                            <a  style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
                        </div>
                        <div id="collapse6" class="panel-collapse collapse noCrossRef" aria-expanded="false">
                             <div class="panel-body">
							 <h4>Description:</h4>
								<p>This web-service enables a third party application to get (read) the data of a specific learning object available for the current authenticated learner.<a href="/api_web_services_list_and_details.html#learner_learning_objects_item_get">Click here to see how it works.</a></p>
								</div></div>
                        
                    </div>
                    <!-- /.panel -->
                    <div class="panel panel-default">
                        <div class="panel-heading">
                            <h4 class="panel-title" id="
aenean-consequat-lorem-ut-felis-ullamcorper
">
                                <a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion3" href="#collapse7" aria-expanded="false">/LearningObjects/Themes/get</a>
                            <a  style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
                        </div>
                        <div id="collapse7" class="panel-collapse collapse noCrossRef" aria-expanded="false">
                                                          <div class="panel-body">

							 <h4>Description:</h4>
								<p>This web-service enables a third party application to get (read) the data of themes for learning objects available for the current authenticated learner .<a href="/api_web_services_list_and_details.html#learner_learning_objects_themes_get">Click here to see how it works.</a></p>
								</div></div>
                        </div>
                    </div>

                    <!-- /.panel -->
                    <div class="panel panel-default">
                        <div class="panel-heading">
                            <h4 class="panel-title" id="
curabitur-eget-leo-at-velit-imperdiet-varius-in-eu-ipsum-vitae-1">
                                <a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion3" href="#collapse8" aria-expanded="false">/LearningObjects/Types/get</a>
                            <a   style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
                        </div>
                        <div id="collapse8" class="panel-collapse collapse" aria-expanded="false">
                            <div class="panel-body">
<h4>Description:</h4>
								<p>This web-service enables a third party application to get (read) the learning objects's type available for the current authenticated learner.<a href="/api_web_services_list_and_details.html#learner_learning_objects_types_get">Click here to see how it works.</a></p>
								                            </div>
                        </div>
                    </div>
					
					<!-- /.panel -->
                    <div class="panel panel-default">
                        <div class="panel-heading">
                            <h4 class="panel-title" id="
curabitur-eget-leo-at-velit-imperdiet-varius-in-eu-ipsum-vitae-1">
                                <a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion3" href="#collapse9" aria-expanded="false">/LearningObjects/Download/get</a>
                            <a   style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
                        </div>
                        <div id="collapse9" class="panel-collapse collapse" aria-expanded="false">
                            <div class="panel-body">
<h4>Description:</h4>
								<p>This web-service enables a third party application to download a specific learning object on the device of the current authenticated learner.<a href="/api_web_services_list_and_details.html#learner_learning_objects_download_item_get">Click here to see how it works.</a></p>
								                            </div>
                        </div>
                    </div>
					
					<div class="panel panel-default">
                        <div class="panel-heading">
                            <h4 class="panel-title" id="
curabitur-eget-leo-at-velit-imperdiet-varius-in-eu-ipsum-vitae-1">
                                <a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion3" href="#collapse10" aria-expanded="false">/LearningObjects/Comment/Vote</a>
                            <a   style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
                        </div>
                        <div id="collapse10" class="panel-collapse collapse" aria-expanded="false">
                            <div class="panel-body">
<h4>Description:</h4>
								<p>This web-service enables a third party application to allow an authenticated learner to vote for a learning object.<a href="/api_web_services_list_and_details.html#learner_learning_objects_item_post">Click here to see how it works.</a></p>
								                            </div>
                        </div>
                    </div>
					
	</div>
	<div role="tabpanel" class="tab-pane" id="tracking">
		
		<div class="panel-group" id="accordion4">
		<!-- /.panel -->
		<div class="panel panel-default">
			<div class="panel-heading">
				<h4 class="panel-title" id="
curabitur-eget-leo-at-velit-imperdiet-varius-in-eu-ipsum-vitae-1">
					<a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion4" href="#collapse11" aria-expanded="false">/Tracking/get</a>
				<a   style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
			</div>
			<div id="collapse11" class="panel-collapse collapse" aria-expanded="false">
				<div class="panel-body">
					<h4>Description:</h4>
					<p>This web-service enables a third party application to get (read) the tracking data (report) on learning object available for the current authenticated learner.<a href="/api_web_services_list_and_details.html#learner_tracking_item_get">Click here to see how it works.</a></p>
												</div>
			</div>
		</div>
		<div class="panel panel-default">
			<div class="panel-heading">
				<h4 class="panel-title" id="
curabitur-eget-leo-at-velit-imperdiet-varius-in-eu-ipsum-vitae-1">
					<a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion4" href="#collapse139" aria-expanded="false">/Tracking/post</a>
				<a   style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
			</div>
			<div id="collapse139" class="panel-collapse collapse" aria-expanded="false">
				<div class="panel-body">
					<h4>Description:</h4>
					<p>This web-service enables a third party application to set/ update the tracking data (report) on learning object available for the current authenticated learner.<a href="/api_web_services_list_and_details.html#learner_tracking_item_post">Click here to see how it works.</a></p>
												</div>
			</div>
		</div>
		<!-- /.panel -->
		<div class="panel panel-default">
			<div class="panel-heading">
				<h4 class="panel-title" id="
curabitur-eget-leo-at-velit-imperdiet-varius-in-eu-ipsum-vitae-1">
					<a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion4" href="#collapse38" aria-expanded="false">/Trackings/post</a>
				<a   style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
			</div>
			<div id="collapse38" class="panel-collapse collapse" aria-expanded="false">
				<div class="panel-body">
					<h4>Description:</h4>
					<p>This web-service enables a third party application to get/set/update the trackings data (report)  for the current authenticated learner.<a href="/api_web_services_list_and_details.html#learner_trackings_post">Click here to see how it works.</a></p>
												</div>
			</div>
		</div>
		</div>			
	</div>
	<div role="tabpanel" class="tab-pane" id="discussion">

		<div class="panel-group" id="accordion5">

		<!-- /.panel -->
		<div class="panel panel-default">
			<div class="panel-heading">
				<h4 class="panel-title" id="
curabitur-eget-leo-at-velit-imperdiet-varius-in-eu-ipsum-vitae-1">
					<a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion5" href="#collapse12" aria-expanded="false">/Discussions/get</a>
				<a   style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
			</div>
			<div id="collapse12" class="panel-collapse collapse" aria-expanded="false">
				<div class="panel-body">
					<h4>Description:</h4>
					<p>This web-service enables a third party application to get (read) available discussions of the current authenticated learner and their comments. The discussions are returned from the newest to the oldest, accordingly to their visibility and the optionnal filter on context. Comments for a given discussion are returned from the newest to the oldest as well..<a href="/api_web_services_list_and_details.html#learner_discussions_get">Click here to see how it works.</a></p>
												</div>
			</div>
		</div>
		<div class="panel panel-default">
			<div class="panel-heading">
				<h4 class="panel-title" id="
curabitur-eget-leo-at-velit-imperdiet-varius-in-eu-ipsum-vitae-1">
					<a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion5" href="#collapse39" aria-expanded="false">/Discussions/post</a>
				<a   style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
			</div>
			<div id="collapse39" class="panel-collapse collapse" aria-expanded="false">
				<div class="panel-body">
					<h4>Description:</h4>
					<p>This web-service enables a third party application to set a discussion for the current authenticated learner.<a href="/api_web_services_list_and_details.html#learner_discussions_post">Click here to see how it works.</a></p>
												</div>
			</div>
		</div>
		
		<div class="panel panel-default">
			<div class="panel-heading">
				<h4 class="panel-title" id="
curabitur-eget-leo-at-velit-imperdiet-varius-in-eu-ipsum-vitae-1">
					<a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion5" href="#collapse40" aria-expanded="false">/Discussions/item/post</a>
				<a   style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
			</div>
			<div id="collapse40" class="panel-collapse collapse" aria-expanded="false">
				<div class="panel-body">
					<h4>Description:</h4>
					<p>This web-service enables a third party application to set a new comment to a specific discussion for the current authenticated learner.<a href="/api_web_services_list_and_details.html#learner_discussions_item_post">Click here to see how it works.</a></p>
												</div>
			</div>
		</div>
		
		<!-- /.panel -->
		<div class="panel panel-default">
			<div class="panel-heading">
				<h4 class="panel-title" id="
curabitur-eget-leo-at-velit-imperdiet-varius-in-eu-ipsum-vitae-1">
					<a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion5" href="#collapse13" aria-expanded="false">/Discussions/Comments/Item/put</a>
				<a   style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
			</div>
			<div id="collapse13" class="panel-collapse collapse" aria-expanded="false">
				<div class="panel-body">
					<h4>Description:</h4>
					<p>This web-service enables a third party application the current authenticated learner to like or dislike a comment.<a href="/api_web_services_list_and_details.html#learner_discussions_comment_like_put">Click here to see how it works.</a></p>
												</div>
			</div>
		</div>
					
	
		<!-- /.panel -->
		<div class="panel panel-default">
			<div class="panel-heading">
				<h4 class="panel-title" id="
curabitur-eget-leo-at-velit-imperdiet-varius-in-eu-ipsum-vitae-1">
					<a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion5" href="#collapse14" aria-expanded="false">/Discussions/Follow/post</a>
				<a   style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
			</div>
			<div id="collapse14" class="panel-collapse collapse" aria-expanded="false">
				<div class="panel-body">
					<h4>Description:</h4>
					<p>This web-service enables a third party application to subscribe the current authenticated for the following of a given discussion.<a href="/api_web_services_list_and_details.html#learner_discussions_follow_post">Click here to see how it works.</a></p>
												</div>
			</div>
		</div>
		</div>			
	</div>
	<!--
	<div role="tabpanel" class="tab-pane" id="search">
		
		
		
		
		
		
		<div class="panel-group" id="accordion6">
		
                    <div class="panel panel-default">
                        <div class="panel-heading">
                            <h4 class="panel-title" id="
lorem-ipsum-dolor-sit-amet-consectetur-adipiscing-elit
">
                                <a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion6" href="#collapse15" aria-expanded="false">/searchFilters/get</a>
                            <a   style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
                        </div>
                        <div id="collapse15" class="panel-collapse collapse noCrossRef" aria-expanded="false">
                            <div class="panel-body">
                                <h4>Description:</h4>
								<p>This web-service enables a third party application to search for values in Training or learning Object context for the current authenticated learner.<a href="/api_web_services_list_and_details.html#learner_search_filters_get">Click here to see how it works.</a></p>
								</div>
                        </div>
                    </div>

					
	</div>
	</div>-->
	
</div>


## Administration API

The web-services that are part of the CrossKnowledge Administration API give the possibility to get and set data into CrossKnowledge platform data in order to improve business workflow by  :

* Building custom business logic outside the CrossKnowledge platform,
* Creating specific learning data analytics dashboard,
* and more.


{% include callout.html content="<span class='fa-stack fa-lg'><i class='fa fa-circle fa-stack-2x'></i><i class='fa fa-key fa-stack-1x fa-inverse'></i></span>&nbsp;Get your [CrossKnowledge Learning Suite API key now](/http://page.crossknowledge.com/contact-EN.html) to use the Administration API." type="info" %}


<ul id="profileTabs" class="nav nav-tabs">
	<li class="active" ><a href="#learners" data-toggle="tab">Learner</a></li>
	<li><a href="#entity" data-toggle="tab">Entity</a></li>
    <li><a href="#training" data-toggle="tab">Training</a></li>
    <li><a href="#session" data-toggle="tab">(Training) Sessions</a></li>
	<li><a href="#registration" data-toggle="tab">Registrations</a></li>
	<li><a href="#content" data-toggle="tab">Content</a></li>
    <li><a href="#report" data-toggle="tab">Report</a></li>
	<li><a href="#admin" data-toggle="tab">Admins</a></li>
	
</ul>
  <div class="tab-content">
	<div role="tabpanel" class="tab-pane active" id="learner">
		
		<div class="panel-group" id="accordion7">
		
                    <div class="panel panel-default">
                        <div class="panel-heading">
                            <h4 class="panel-title" id="
lorem-ipsum-dolor-sit-amet-consectetur-adipiscing-elit
">
                                <a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion7" href="#collapse16" aria-expanded="false">/Learner/get</a>
                            <a   style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
                        </div>
                        <div id="collapse16" class="panel-collapse collapse noCrossRef" aria-expanded="false">
                            <div class="panel-body">
                                <h4>Description:</h4>
								<p>This web-service enables a third party application to get the data of a specific learner account existing in the CrossKnowledge platform.<a href="/api_web_services_list_and_details_admins.html#offline_learner_get">Click here to see how it works.</a></p>
								</div>
                        </div>
                    </div>
					<div class="panel panel-default">
                        <div class="panel-heading">
                            <h4 class="panel-title" id="
lorem-ipsum-dolor-sit-amet-consectetur-adipiscing-elit
">
                                <a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion7" href="#collapse17" aria-expanded="false">/Learner/list/get</a>
                            <a   style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
                        </div>
                        <div id="collapse17" class="panel-collapse collapse noCrossRef" aria-expanded="false">
                            <div class="panel-body">
                                <h4>Description:</h4>
								<p>This web-service enables a third party application to list the data of learners accounts existing in the CrossKnowledge platform.<a href="/api_web_services_list_and_details_admins.html#offline_learner_get">Click here to see how it works.</a></p>
								</div>
                        </div>
                    </div>
					<div class="panel panel-default">
                        <div class="panel-heading">
                            <h4 class="panel-title" id="
lorem-ipsum-dolor-sit-amet-consectetur-adipiscing-elit
">
                                <a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion7" href="#collapse18" aria-expanded="false">/Learner/add/post</a>
                            <a   style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
                        </div>
                        <div id="collapse18" class="panel-collapse collapse noCrossRef" aria-expanded="false">
                            <div class="panel-body">
                                <h4>Description:</h4>
								<p>This web-service enables a third party application to add (insert) a new learner account in the CrossKnowledge platform.<a href="/api_web_services_list_and_details_admins.html#offline_learner_post">Click here to see how it works.</a></p>
								</div>
                        </div>
                    </div>
					<div class="panel panel-default">
                        <div class="panel-heading">
                            <h4 class="panel-title" id="
lorem-ipsum-dolor-sit-amet-consectetur-adipiscing-elit
">
                                <a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion7" href="#collapse19" aria-expanded="false">/Learner/update/put</a>
                            <a   style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
                        </div>
                        <div id="collapse19" class="panel-collapse collapse noCrossRef" aria-expanded="false">
                            <div class="panel-body">
                                <h4>Description:</h4>
								<p>This web-service enables a third party application to edit (update) the data of a specific learner account existing in the CrossKnowledge platform.<a href="/api_web_services_list_and_details_admins.html#offline_learner_put">Click here to see how it works.</a></p>
								</div>
                        </div>
                    </div>
					<div class="panel panel-default">
                        <div class="panel-heading">
                            <h4 class="panel-title" id="
lorem-ipsum-dolor-sit-amet-consectetur-adipiscing-elit
">
                                <a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion7" href="#collapse20" aria-expanded="false">/Learner/registrations/get</a>
                            <a   style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
                        </div>
                        <div id="collapse20" class="panel-collapse collapse noCrossRef" aria-expanded="false">
                            <div class="panel-body">
                                <h4>Description:</h4>
								<p>This web-service enables a third party application to get (read) the data registrations of a specific learner account.<a href="/api_web_services_list_and_details_admins.html#offline_learner_registration_get">Click here to see how it works.</a></p>
								</div>
                        </div>
                    </div>
					<div class="panel panel-default">
                        <div class="panel-heading">
                            <h4 class="panel-title" id="
lorem-ipsum-dolor-sit-amet-consectetur-adipiscing-elit
">
                                <a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion7" href="#collapse21" aria-expanded="false">/Learner/AuthToken/get</a>
                            <a   style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
                        </div>
                        <div id="collapse21" class="panel-collapse collapse noCrossRef" aria-expanded="false">
                            <div class="panel-body">
                                <h4>Description:</h4>
								<p>This web-service enables a third party application to get an authorization token for a specific learner account.<a href="/api_web_services_list_and_details_admins.html#offline_learner_token_get">Click here to see how it works.</a></p>
								{% include note.html content="This authorization token can be used to [authenticate](/ckauth_workflow.html) the learner in order to call out the Learner API web-services." %}

								
								</div>
                        </div>
                    </div>

					
	</div>
	
	</div>
	<div role="tabpanel" class="tab-pane" id="entity">
		<div class="panel-group" id="accordion13">
		
				<div class="panel panel-default">
                        <div class="panel-heading">
                            <h4 class="panel-title" id="
lorem-ipsum-dolor-sit-amet-consectetur-adipiscing-elit
">
                                <a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion13" href="#collapse39" aria-expanded="false">/Entity/get</a>
                            <a   style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
                        </div>
                        <div id="collapse39" class="panel-collapse collapse noCrossRef" aria-expanded="false">
                            <div class="panel-body">
                                <h4>Description:</h4>
								<p>This web-service enables a third party application to get the data of an existing entity in the CrossKnowledge platform.<a href="/api_web_services_list_and_details_admins.html#offline_entity_get">Click here to see how it works.</a></p>

								
								</div>
                        </div>
                    </div>
					
					<div class="panel panel-default">
                        <div class="panel-heading">
                            <h4 class="panel-title" id="
lorem-ipsum-dolor-sit-amet-consectetur-adipiscing-elit
">
                                <a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion14" href="#collapse40" aria-expanded="false">/Entity/list/get</a>
                            <a   style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
                        </div>
                        <div id="collapse40" class="panel-collapse collapse noCrossRef" aria-expanded="false">
                            <div class="panel-body">
                                <h4>Description:</h4>
								<p>This web-service enables a third party application to list the data of all existing entities in the CrossKnowledge platform.<a href="/api_web_services_list_and_details_admins.html#offline_entity_list">Click here to see how it works.</a></p>

								
								</div>
                        </div>
                    </div>
		</div>
	</div>
	<div role="tabpanel" class="tab-pane" id="training">
		<div class="panel-group" id="accordion8">
		
				<div class="panel panel-default">
                        <div class="panel-heading">
                            <h4 class="panel-title" id="
lorem-ipsum-dolor-sit-amet-consectetur-adipiscing-elit
">
                                <a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion8" href="#collapse21" aria-expanded="false">/Training/list/get</a>
                            <a   style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
                        </div>
                        <div id="collapse21" class="panel-collapse collapse noCrossRef" aria-expanded="false">
                            <div class="panel-body">
                                <h4>Description:</h4>
								<p>This web-service enables a third party application to list all the trainings existing in the CrossKnowledge platform.<a href="/api_web_services_list_and_details_admins.html#offline_training_list">Click here to see how it works.</a></p>

								
								</div>
                        </div>
                    </div>
			<div class="panel panel-default">
                        <div class="panel-heading">
                            <h4 class="panel-title" id="
lorem-ipsum-dolor-sit-amet-consectetur-adipiscing-elit
">
                                <a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion8" href="#collapse22" aria-expanded="false">/Training/get</a>
                            <a   style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
                        </div>
                        <div id="collapse22" class="panel-collapse collapse noCrossRef" aria-expanded="false">
                            <div class="panel-body">
                                <h4>Description:</h4>
								<p>This web-service enables a third party application to get (read) the metadata of an existing training in the CrossKnowledge platform.<a href="/api_web_services_list_and_details_admins.html#offline_training_get">Click here to see how it works.</a></p>

								
								</div>
                        </div>
                    </div>
					<div class="panel panel-default">
                        <div class="panel-heading">
                            <h4 class="panel-title" id="
lorem-ipsum-dolor-sit-amet-consectetur-adipiscing-elit
">
                                <a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion8" href="#collapse23" aria-expanded="false">/Training/add/post</a>
                            <a   style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
                        </div>
                        <div id="collapse23" class="panel-collapse collapse noCrossRef" aria-expanded="false">
                            <div class="panel-body">
                                <h4>Description:</h4>
								<p>This web-service enables a third party application to add( insert) a new training in the CrossKnowledge platform.<a href="/api_web_services_list_and_details_admins.html#offline_training_post">Click here to see how it works.</a></p>

								
								</div>
                        </div>
                    </div>
					<div class="panel panel-default">
                        <div class="panel-heading">
                            <h4 class="panel-title" id="
lorem-ipsum-dolor-sit-amet-consectetur-adipiscing-elit
">
                                <a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion8" href="#collapse24" aria-expanded="false">/Training/update/put</a>
                            <a   style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
                        </div>
                        <div id="collapse24" class="panel-collapse collapse noCrossRef" aria-expanded="false">
                            <div class="panel-body">
                                <h4>Description:</h4>
								<p>This web-service enables a third party application to edit (update) the meatadata of an existing training in the CrossKnowledge platform.<a href="/api_web_services_list_and_details_admins.html#offline_training_put">Click here to see how it works.</a></p>

								
								</div>
                        </div>
                    </div>
					
		</div>
	</div>
	<div role="tabpanel" class="tab-pane" id="session">
		<div class="panel-group" id="accordion9">
		
				<div class="panel panel-default">
                        <div class="panel-heading">
                            <h4 class="panel-title" id="
lorem-ipsum-dolor-sit-amet-consectetur-adipiscing-elit
">
                                <a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion9" href="#collapse25" aria-expanded="false">/Session/list/get</a>
                            <a   style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
                        </div>
                        <div id="collapse25" class="panel-collapse collapse noCrossRef" aria-expanded="false">
                            <div class="panel-body">
                                <h4>Description:</h4>
								<p>This web-service enables a third party application list to all the sessions existing in the CrossKnowledge platform.<a href="/api_web_services_list_and_details_admins.html#offline_session_list_get">Click here to see how it works.</a></p>

								
								</div>
                        </div>
                    </div>
			<div class="panel panel-default">
                        <div class="panel-heading">
                            <h4 class="panel-title" id="
lorem-ipsum-dolor-sit-amet-consectetur-adipiscing-elit
">
                                <a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion9" href="#collapse26" aria-expanded="false">/Session/get</a>
                            <a   style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
                        </div>
                        <div id="collapse26" class="panel-collapse collapse noCrossRef" aria-expanded="false">
                            <div class="panel-body">
                                <h4>Description:</h4>
								<p>This web-service enables a third party application to get (read) the metadata of an existing session in the CrossKnowledge platform.<a href="/api_web_services_list_and_details_admins.html#offline_session_get">Click here to see how it works.</a></p>

								
								</div>
                        </div>
                    </div>
					<div class="panel panel-default">
                        <div class="panel-heading">
                            <h4 class="panel-title" id="
lorem-ipsum-dolor-sit-amet-consectetur-adipiscing-elit
">
                                <a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion9" href="#collapse27" aria-expanded="false">/Session/add/post</a>
                            <a   style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
                        </div>
                        <div id="collapse27" class="panel-collapse collapse noCrossRef" aria-expanded="false">
                            <div class="panel-body">
                                <h4>Description:</h4>
								<p>This web-service enables a third party application to add( update) a new session in the CrossKnowledge platform.<a href="/api_web_services_list_and_details_admins.html#offline_session_post">Click here to see how it works.</a></p>

								
								</div>
                        </div>
                    </div>
					<div class="panel panel-default">
                        <div class="panel-heading">
                            <h4 class="panel-title" id="
lorem-ipsum-dolor-sit-amet-consectetur-adipiscing-elit
">
                                <a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion9" href="#collapse28" aria-expanded="false">/Session/update/put</a>
                            <a   style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
                        </div>
                        <div id="collapse28" class="panel-collapse collapse noCrossRef" aria-expanded="false">
                            <div class="panel-body">
                                <h4>Description:</h4>
								<p>This web-service enables a third party application to edit (update) the metadata of an existing session in the CrossKnowledge platform.<a href="/api_web_services_list_and_details_admins.html#offline_session_put">Click here to see how it works.</a></p>

								
								</div>
                        </div>
                    </div>
					<div class="panel panel-default">
                        <div class="panel-heading">
                            <h4 class="panel-title" id="
lorem-ipsum-dolor-sit-amet-consectetur-adipiscing-elit
">
                                <a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion9" href="#collapse29" aria-expanded="false">/Session/register/post</a>
                            <a   style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
                        </div>
                        <div id="collapse29" class="panel-collapse collapse noCrossRef" aria-expanded="false">
                            <div class="panel-body">
                                <h4>Description:</h4>
								<p>This web-service allow to register/ enroll a learner to an existing session in the CrossKnowledge platform.<a href="/api_web_services_list_and_details_admins.html#offline_training_session_register_learner_post">Click here to see how it works.</a></p>

								
								</div>
                        </div>
                    </div>
					
		</div>
	</div>
	<div role="tabpanel" class="tab-pane" id="registration">
			<div class="panel-group" id="accordion10">

				<div class="panel panel-default">
					<div class="panel-heading">
						<h4 class="panel-title" id="
lorem-ipsum-dolor-sit-amet-consectetur-adipiscing-elit
">
							<a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion10" href="#collapse30" aria-expanded="false">/Registration/get</a>
						<a   style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
					</div>
					<div id="collapse30" class="panel-collapse collapse noCrossRef" aria-expanded="false">
						<div class="panel-body">
							<h4>Description:</h4>
							<p>This web-service enables a third party application to get a registration existing in the CrossKnowledge platform.<a href="/api_web_services_list_and_details_admins.html#offline_registration_get">Click here to see how it works.</a></p>

							
							</div>
					</div>
				</div>
				
				<!--<div class="panel panel-default">
					<div class="panel-heading">
						<h4 class="panel-title" id="
lorem-ipsum-dolor-sit-amet-consectetur-adipiscing-elit
">
							<a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion10" href="#collapse30" aria-expanded="false">/Registration/report/get</a>
						<a   style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
					</div>
					<div id="collapse30" class="panel-collapse collapse noCrossRef" aria-expanded="false">
						<div class="panel-body">
							<h4>Description:</h4>
							<p>This web-service enables a third party application to get the report list exisitng in the CrossKnowledge platform for a specific registration.<a href="/api_web_services_list_and_details_admins.html#offline_registration_report_get">Click here to see how it works.</a></p>

							
							</div>
					</div>
				</div>-->
				
				<div class="panel panel-default">
					<div class="panel-heading">
						<h4 class="panel-title" id="
lorem-ipsum-dolor-sit-amet-consectetur-adipiscing-elit
">
							<a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion10" href="#collapse31" aria-expanded="false">/Registration/delete</a>
						<a   style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
					</div>
					<div id="collapse31" class="panel-collapse collapse noCrossRef" aria-expanded="false">
						<div class="panel-body">
							<h4>Description:</h4>
							<p>This web-service enables a third party application to delete a specific registration existing in the CrossKnowledge platform.<a href="/api_web_services_list_and_details_admins.html#offline_registration_delete">Click here to see how it works.</a></p>

							
							</div>
					</div>
				</div>
			</div>
	</div>
	<div role="tabpanel" class="tab-pane" id="content">
		<div class="panel-group" id="accordion11">

			<div class="panel panel-default">
						<div class="panel-heading">
							<h4 class="panel-title" id="
	lorem-ipsum-dolor-sit-amet-consectetur-adipiscing-elit
	">
								<a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion11" href="#collapse33" aria-expanded="false">/Content/get</a>
							<a   style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
						</div>
						<div id="collapse33" class="panel-collapse collapse noCrossRef" aria-expanded="false">
							<div class="panel-body">
								<h4>Description:</h4>
								<p>This web-service enables a third party application to get the metadata of learning object in the CrossKnowledge platform.<a href="/api_web_services_list_and_details_admins.html#offline_content_get">Click here to see how it works.</a></p>

								
								</div>
						</div>
			</div>
			<div class="panel panel-default">
						<div class="panel-heading">
							<h4 class="panel-title" id="
	lorem-ipsum-dolor-sit-amet-consectetur-adipiscing-elit
	">
								<a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion11" href="#collapse34" aria-expanded="false">/Content/list/get</a>
							<a   style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
						</div>
						<div id="collapse34" class="panel-collapse collapse noCrossRef" aria-expanded="false">
							<div class="panel-body">
								<h4>Description:</h4>
								<p>This web-service enables a third party application to list the metadatas of all the learning objects existing in the CrossKnowledge platform.<a href="/api_web_services_list_and_details_admins.html#offline_content_list">Click here to see how it works.</a></p>

								
								</div>
						</div>
			</div>
		</div>		
	</div>
	<!--
	<div role="tabpanel" class="tab-pane" id="report">
		
		<div class="panel-group" id="accordion12">

			<div class="panel panel-default">
							<div class="panel-heading">
								<h4 class="panel-title" id="
		lorem-ipsum-dolor-sit-amet-consectetur-adipiscing-elit
		">
									<a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion12" href="#collapse35" aria-expanded="false">/Report/get</a>
								<a   style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
							</div>
							<div id="collapse35" class="panel-collapse collapse noCrossRef" aria-expanded="false">
								<div class="panel-body">
									<h4>Description:</h4>
									<p>This web-service enables a third party application to get data of an existing report (tracking data)  in the CrossKnowledge platform.<a href="/api_web_services_list_and_details_admins.html#offline_report_get">Click here to see how it works.</a></p>

									
									</div>
							</div>
				</div>
			
		</div>
			
	</div>-->
	<div role="tabpanel" class="tab-pane" id="admin">
		
		<div class="panel-group" id="accordion12">

			<div class="panel panel-default">
							<div class="panel-heading">
								<h4 class="panel-title" id="
		lorem-ipsum-dolor-sit-amet-consectetur-adipiscing-elit
		">
									<a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion12" href="#collapse36" aria-expanded="false">/Administrator/AutoConnectionURL/get</a>
								<a   style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
							</div>
							<div id="collapse36" class="panel-collapse collapse noCrossRef" aria-expanded="false">
								<div class="panel-body">
									<h4>Description:</h4>
									<p>This web-service enables a third party application to get a secured authentication URL (SSO) for a specific administrator account existing in the CrossKnowledge platform.<a href="/api_web_services_list_and_details_admins.html#offline_administrator_login_get">Click here to see how it works.</a></p>

									
									</div>
							</div>
				</div>
				
				<div class="panel panel-default">
							<div class="panel-heading">
								<h4 class="panel-title" id="
		lorem-ipsum-dolor-sit-amet-consectetur-adipiscing-elit
		">
									<a class="noCrossRef accordion-toggle collapsed" data-toggle="collapse" data-parent="#accordion12" href="#collapse37" aria-expanded="false">/Administrator/update/put</a>
								<a   style="font-family: anchorjs-icons; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: normal; line-height: 1; padding-left: 0.375em;"></a></h4>
							</div>
							<div id="collapse37" class="panel-collapse collapse noCrossRef" aria-expanded="false">
								<div class="panel-body">
									<h4>Description:</h4>
									<p>This web-service enables a third party application to edit (update) an existing administrator account in the CrossKnowledge platform.<a href="/api_web_services_list_and_details_admins.html#offline_administrator_put">Click here to see how it works.</a></p>

									
									</div>
							</div>
				</div>
			
		</div>
		
		
	</div>
</div>
