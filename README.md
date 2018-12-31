### Setup
- [Requesting Optimove Web SDK](#requesting) 
- [Add GDN related functions](#add-functions) 
### Reference
- [Optimove-Google Display Network Integration](https://docs.optimove.com/google-display-network-integration/)

<hr>

### <a id="requesting"></a>Requesting Optimove Web SDK
Request [Optimove Web SDK](https://github.com/optimoveproductintegration/Web-SDK-Integration-Guide) from your CSM or Optimove point of contact and send them the following information:

 1. [Approving Optimove as a User List Provider](https://docs.optimove.com/google-display-network-integration/)   (see step #1)
 2.  [Getting your AdWords/DBM Account Details](https://docs.optimove.com/google-display-network-integration/)   (see step #2) 

Once the Product Integration team receives the request details , they will send you your SDK details for implementation
 > You must have an Optimove site live in production
<hr>

### <a id="add-functions"></a>Add GDN related functions

Add the [Web SDK](https://github.com/optimoveproductintegration/Web-SDK-Integration-Guide) functions into your code with the details the Product Integration team sent you:

 1. Call [`optimoveSDK.initialize()`](https://github.com/optimove-tech/Web-SDK-Integration-Guide#add-code) function to initialize the SDK
 2. Call [`optimoveSDK.API.setPageVisit()`](https://github.com/optimove-tech/Web-SDK-Integration-Guide#track-visits) function to report page visits
 3. Call [`optimoveSDK.API.setUserId()`](https://github.com/optimove-tech/Web-SDK-Integration-Guide#link-visit-customer) or [`optimoveSDK.API.registerUser()`](https://github.com/optimove-tech/Web-SDK-Integration-Guide#record-user-email) in order to link/stitch visitor to customerID for Optimove campaigns
>**Notes:** 
> - Please contact the Product Integration Team to guide you on which functions to use
> - Use the [Web SDK](https://github.com/optimoveproductintegration/Web-SDK-Integration-Guide) guide to see detailed information on the above functions
> - Optimove GDN support is done via Optimove [Web SDK](https://github.com/optimoveproductintegration/Web-SDK-Integration-Guide) SDK only

<br/>

>**Technical explanation:** 
> - The functions above sets a cookie for each site visitor containing your Customer ID or Visitor ID, under the Google Cookie Matching service domain. 
> - It also sends a pixel request to the specified Google domain, receiving in return a redirect request to the Optimove’s cookie matching service, containing the Google ID of the customer. 
> - This allows Optimove to match the Google ID received with your existing Customer ID or assigned Visitor ID, thus identifying the customer/visitor within the Optimove data warehouse.
