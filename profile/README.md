# Everyone's a Critic
<a href="https://apps.apple.com/us/app/everyones-a-critic/id6444014131">
    <img src="images/download-on-the-app-store.png" height="40" alt="Download">
</a>

## Summary
Everyone's a Critic is a mobile app that allows users to rate their favorite products and makes recommendations based on their tastes. Created on the premise that taste is individualistic, in a world that celebrates conformity.

## Feature Roadmap
- [x] A new user should be able to enroll in a variety of available communities aligned with their interest
- [x] A user with multiple enrolled communities should be able to navigate between their enrolled communities
- [x] A user should be able to browse products within a community, discovering new products to try and rate
- [x] A user should be able to view product details, with displayed product attributes variable depending on the community and product itself
- [x] A user should be able to rate products, providing basic details on their experience with the product and a numeric score summarizing that experience
- [x] A user should be able to browse products they've rated, easily seeing which products they liked and disliked
- [ ] A user should be able to browse a wide variety of products within each community. Curated communities should have a wide breadth of products available within commmon brands specific to that community.
- [ ] A user should be able to perform a text search to find a product
- [ ] A user should be able to search for a product by taking a picture of the product's label via an integration with Vuforia Cloud Recognition Service
- [ ] A user should be able to view recommended products based on their location and product rating data
- [ ] A user should be able to create products missing from the community by uploading a picture and providing basic product details

## Key User Flows
### New User
<p float="left">
    <img src="images/new-user-flow/sign-up.png" height="300" alt="Sign Up">
    <img src="images/new-user-flow/confirm-account.png" height="300" alt="Confirm Account">
    <img src="images/new-user-flow/sign-in.png" height="300" alt="Sign In">
    <img src="images/new-user-flow/community-enrollment.png" height="300" alt="Community Management">
</p>

1. User Signs Up
1. User receives a confirmation code to their email and enters it in the app
1. User Signs In
1. User is routed to the Community Management page

### Join Community
<p float="left">
    <img src="images/join-community-flow/start.png" height="300" alt="Start">
    <img src="images/join-community-flow/tap-to-add.png" height="300" alt="Tap to Add">
    <img src="images/join-community-flow/end.png" height="300" alt="End">
</p>

1. User is routed to the Community Management page
1. User finds a featured commmunity or searches for a specific community and taps it to join
1. Community moves to the "Your Communities" section

### Leave Community
<p float="left">
    <img src="images/leave-community-flow/start.png" height="300" alt="Start">
    <img src="images/leave-community-flow/swipe-to-delete.png" height="300" alt="Swipe to Delete">
    <img src="images/leave-community-flow/tap-to-confirm-deletion.png" height="300" alt="Tap to Confirm Deletion">
    <img src="images/leave-community-flow/end.png" height="300" alt="End">
</p>

1. User is routed to the Community Management page
1. User swipes left on an enrolled commmunity, exposing the delete button
1. User taps on the delete button to confirm the deletion
1. Community is removed from the "Your Communities" section

### Enter Community
<p float="left">
    <img src="images/enter-community-flow/start.png" height="300" alt="Start">
    <img src="images/enter-community-flow/tap-to-enter.png" height="300" alt="Tap to Enter">
    <img src="images/enter-community-flow/end.png" height="300" alt="Community Home">
</p>

1. User is routed to the Community Management page
1. User taps on an enrolled community
1. User is routed to the Community Home page

### Existing User App Start-up
<p float="left">
    <img src="images/existing-user-flow/logo-splash.png" height="300" alt="Logo Splash">
    <img src="images/existing-user-flow/community-splash.png" height="300" alt="Community Splash">
    <img src="images/existing-user-flow/community-home.png" height="300" alt="Community Home">
</p>

1. Everyone's a Critic logo displays during data load
1. If there are saved user credentials, the logo of the user's last viewed community displays
1. User is routed to the home page of their last viewed community

### Add Rating
<p float="left">
    <img src="images/add-rating-flow/tap-product.png" height="300" alt="Tap Product">
    <img src="images/add-rating-flow/product-home.png" height="300" alt="Product Home">
    <img src="images/add-rating-flow/tap-to-rate.png" height="300" alt="Tap to Rate">
    <img src="images/add-rating-flow/add-rating-details.png" height="300" alt="Add Rating Details">
</p>

1. While browsing products, user taps on a product
1. User is routed to the Product home page
1. User taps on a rating icon to rate the product
1. User enters rating details

### Switch Community
<p float="left">
    <img src="images/switch-community-flow/tap-header.png" height="300" alt="Tap Header">
    <img src="images/switch-community-flow/switch-community.png" height="300" alt="Community Management Page">
    <img src="images/switch-community-flow/tap-community.png" height="300" alt="Tap Community">
    <img src="images/switch-community-flow/community-home.png" height="300" alt="Community Home Page">
</p>

1. From any community page, user taps the header
1. The Community Management page opens as a bottom sheet
1. User taps on a different enrolled community
1. User is routed to the Community Home page


## Tech Stack
### Database
MongoDB, AWS S3
### Backend
Python, Java
### Frontend
React Native, Redux
### Infrastructure:
Managed via Terraform. Microservice architecture built using AWS API Gateway:
* **User Service:** Amazon Cognito
* **Communities Service:** Python, AWS Lambda, Docker
* **Ratings Service:** Java, Spring Boot, Docker, Elastic Container Service creating AWS Fargate tasks hosted on a VPC with monitoring via a Network Load Balancer.
