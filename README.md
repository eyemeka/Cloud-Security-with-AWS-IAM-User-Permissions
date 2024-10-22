# Cloud-Security-with-AWS-IAM-User-Permissions

<!-- wp:image {"id":29,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://eyemekacybersecurityportfolio.wordpress.com/wp-content/uploads/2024/09/architecture.png?w=1024" alt="" class="wp-image-29" /></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2 class="wp-block-heading">Introduction</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>AWS IAM is a service that enables you to manage access to AWS resources securely. IAM allows you to control who is authenticated (signed in) and authorized (has permissions) to use resources within your AWS account. It plays a critical role in ensuring the security of your AWS environment by managing users, groups, roles, and permissions.</p>
<!-- /wp:paragraph -->

<!-- wp:more -->
<!--more-->
<!-- /wp:more -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">Project Overview</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>The goal of this project is to design and implement a robust user permissions management system using AWS Identity and Access Management (IAM). The project aims to create a secure and efficient way to control access to AWS resources, ensuring that users have appropriate levels of access based on their roles and responsibilities within an organization.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">Setting Up Tags</h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>I’ve set up two EC2 instances to test the effectiveness of the permission settings I’ll set up in AWS IAM. I’ve used tags to label them.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>Tags are labels to help AWS Account users identify, and manage their resources. Tags are useful for grouping mass management and applying security policies</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>The tag I’ve used on my EC2 instances is called Env. The value I’ve assigned for my instances are Production and Development. This represent the two different environment that I am using to build and release my work app</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:image {"id":36,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://eyemekacybersecurityportfolio.wordpress.com/wp-content/uploads/2024/09/screenshot-34.png?w=871" alt="" class="wp-image-36" /></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">IAM Policies</h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>IAM Policies are rules that help to allow/deny users /resources permission to perform certain action to my AWS account resources</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>For this project, I’ve set up a policy using the JSON editor.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>I’ve created a Policy that allows all EC2 related actions to all EC2 instances that have the Environment (Env) tag “Dev”. But it also denies creating and deleting tags for ALL EC2 instances</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>When writing JSON Policy statements, you have to specify the:<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>Effect:i.e. Allow or Deny</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Action: i.e. The specific action that we are wanting to Allow or Deny</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Resource: The specific resource/group of resources in my AWS account that this policy will take effect on.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:image {"id":38,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://eyemekacybersecurityportfolio.wordpress.com/wp-content/uploads/2024/09/screenshot-36.png?w=1024" alt="" class="wp-image-38" /></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">AWS Account Alias</h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>New users can get access to my AWS Account through a unique URL created for my account’ Account ID.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>An account alias is a custom name tht i can assign to my AWS account. This custom name would replace my account ID, in my account’s login URL</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>Creating an account alias took me less than a minute</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>Now, my new AWS console sign-in URL is<strong> </strong>https://<strong>myprojectwork-alias-eyemeka</strong>.signin.aws.amazon.com/console</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":40,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://eyemekacybersecurityportfolio.wordpress.com/wp-content/uploads/2024/09/screenshot-37.png?w=1024" alt="" class="wp-image-40" /></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">IAM Users + User Groups</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><span class="OYPEnA font-feature-liga-off font-feature-clig-off font-feature-calt-off text-decoration-none text-strikethrough-none" style="color: rgb(0, 0, 0);font-weight: 600;font-style: normal"></span></p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>IAM Users are other logins or people who have access to my AWS account and these users are created by myself using the AWS IAM service. I can designate other IAM users my access to my AWS resources/services</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>I also created a User Group. User Groups are useful for grouping and managing users permission at a group level. They act similarly to folders when it comes to assigning mass permissions, and policies.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>My User Group is called Myprojectwork-dev-group</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>I attached the Policy I created to this User Group, which means all users that are added to that user group will automatically inherit the user group access permission</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>When I created a new User, I had to tick a checkbox that allow the user access to the AWS Management console</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>Once my new user was set up, there were two ways I could share its sign-in details: Firstly emailing sign-in instructions; secondly downloading a .CSV file</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>My new user had a unique sign-in URL - this is my Account Alias at work!</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:image {"id":44,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://eyemekacybersecurityportfolio.wordpress.com/wp-content/uploads/2024/09/screenshot-38.png?w=1024" alt="" class="wp-image-44" /></figure>
<!-- /wp:image -->

<!-- wp:image {"id":46,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://eyemekacybersecurityportfolio.wordpress.com/wp-content/uploads/2024/09/screenshot-39.png?w=1024" alt="" class="wp-image-46" /></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">IAM User in action</h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>Now with my IAM Policy, IAM User Group and IAM User all set up, let’s put it all together! To do this, I logged into my AWS account as the new user.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>To log in as my IAM User, I had to access the console login URL that was given to me as I set up the new user.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>Once I logged in, I noticed that a lot of panels displayed access denied. This was a clear difference to the dashboard I usually see in my AWS account where I have unrestricted access to resources and it was not denied to access to anything.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:image {"id":51,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://eyemekacybersecurityportfolio.wordpress.com/wp-content/uploads/2024/09/screenshot-40-1.png?w=1024" alt="" class="wp-image-51" /></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">IAM Policies in action</h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>I tested the JSON IAM policy I set up by trying to stop the development and production Instances. When I tried to stop the Production instances, an error message stopped me and explained that I am not authorized to stop the Production Instance.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>When I tried to stop the production instance, an error message stopped me and explained that I am not authorized to stop the Production Instance.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":53,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://eyemekacybersecurityportfolio.wordpress.com/wp-content/uploads/2024/09/screenshot-41.png?w=1024" alt="" class="wp-image-53" /></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">To Summarise</h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>I created:<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>An IAM User Group called <strong>Myprojectwork-dev-group</strong> with defined permissions using an IAM Policy</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>An IAM User called myprojectwork-dev-eyemeka that is added to the user group</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>An EC2 instance with the Env tag Development and Name Myprojectwork-development-eyemeka</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>An EC2 instance with the Env tag Production and Name Myprojectwork-production-eyemeka</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>User was not able to stop, terminate the Production Instance.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->
