Google Display Network is a collection of websites, including specific Google websites like Google Finance, Gmail, Blogger and YouTube, which show AdWords ads. Using either a DoubleClick Bid Manager (DBM) account or an AdWords account with an account manager, you can target “User Lists” of specific users for particular AdWords campaigns, matched by their Google IDs.

The two biggest challenges with effectively using Google user lists for customer retention are (1) deciding which customers to include in each User List, and (2) updating the various User Lists on a frequent basis.

Optimove addresses both of these challenges as part of its core functions: the software allows marketers to identify and manage large numbers of highly-targeted micro-segments (target groups) of customers or website visitors and automatically handles updating the customer or visitor IDs contained in each User List, every day. Updating the User Lists daily maximizes the response rates of customers by always targeting customers with the most relevant messages and incentives, given each customer’s most recent actions and behaviors.

## **Getting Started**
To use Google Display Network as a campaign channel within Optimove, you need to perform the following steps:

### **Approve Optimove as a User List Provider**
To get started, Optimove must be approved as a User List Provider in your AdWords or DBM account with one of the following permission types:

* INVITE_ADVERTISER – User List Provider for a specific brand in your DBM account
* INVITE_PARTNER – User List Provider for all brands in your DMB account
* ADWORDS – User List Provider for simple AdWords accounts

In order to approve Optimove as a User List Provider with one of the above permission types, contact your Google account manager and request to connect Optimove’s AdWords account to your account, specifying your client ID and the type of permission you want to grant Optimove. If you wish to use multiple Google accounts with Optimove, ensure that permissions are granted for each account.

Once this request is passed on to Google, they will connect the Optimove account to your AdWords or DBM account, so that Optimove will be able to create new User Lists and to populate them with customer or visitor IDs.

### **Enabling GDN with Optimove SDK**
In order to use Optimove to automate AdWords campaigns, you need to link, or "match," Google Customer IDs with Optimove Customer IDs and/or Visitor IDs using [Optimove SDK](https://docs.optimove.com/optimove-sdk/). Just follow the steps below to get started:

1. Request [Optimove SDK](https://docs.optimove.com/optimove-sdk/) from your CSM or Optimove point of contact
2. Provide your AdWords/DBM Account Details to Optimove CSM or Point of Contact
In order to connect your Optimove site to the relevant Google account, you need to provide the following information (which Google will provide you) to the Optimove Product Integration team:
* The ClientCustomerID for the Google DMP User List API
* The type of User List Provider assigned to Optimove by Google
Note: If you wish to use multiple Google accounts with Optimove, you will need to provide to the Optimove Product Integration team the ClientCustomerID and User List Provider type for each account.
3. Once the Product Integration team receives the request with #2 above, they will send you your SDK details for implmentation
4. Add the [Optimove SDK](https://docs.optimove.com/optimove-sdk/) to your code with the details the Product Integration team sent you
5. Call `optimoveSDK.initialize()` function to initialize the SDK
6. Call `optimoveSDK.API.setPageVisit()` function to report page visits
7. Call `optimoveSDK.API.setUserID()` in order to link/stitch visitor to customerID for Optimove campaigns

**Note**:
* Use the [Optimove SDK](https://docs.optimove.com/optimove-sdk/) guide to see detailed information on the above functions
* Optimove SDK supports both [Web](https://docs.optimove.com/optimove-sdk/#Website_SDK) and Mobile Native Apps ([Android](https://docs.optimove.com/optimove-sdk/#Android_SDK)/ [iOS](https://docs.optimove.com/optimove-sdk/#iOS_SDK_Swift))
* Cookie matching for website visitors (non-registered users/customers) is only available if you implement [Optimove SDK](https://docs.optimove.com/optimove-sdk/).

**Technical explanation**
* The script above sets a cookie for each site visitor containing your Customer ID or Visitor ID, under the Google Cookie Matching service domain. 
* It also sends a pixel request to the specified Google domain, receiving in return a redirect request to the Optimove’s cookie matching service, containing the Google ID of the customer. 
* This allows Optimove to match the Google ID received with your existing Customer ID or assigned Visitor ID, thus identifying the customer/visitor within the Optimove data warehouse.

### **Create User Lists**
Optimove will automatically create a set of preconfigured User Lists in your connected AdWords or DBM account. If you require the creation of additional User Lists, contact the Optimove integration team. Note that User Lists become active approximately 24 hours after creation.

### **Schedule Your First Google Display Network Campaign**
Once the above steps have been completed, you are ready to run your first Google Display Network campaign: select the “Google Display Network” channel when scheduling a campaign and select the appropriate User List from the drop-down list that appears. In the next step, you will need to associate the User List you selected here with a relevant campaign.
![Schedule Your First Google Display Network Campaign](https://docs.optimove.com/wp-content/uploads/2017/03/word-image-37.png)

From this point on, Optimove will automatically populate the selected Google User List with the customer or visitor IDs included in the selected target group, updated daily. When the campaign’s measurement period concludes, Optimove will remove all IDs from the list.

Note that Optimove will only populate the User List with IDs that were already matched, by the above script, with Google IDs. Thus, a target group may contain 1000 customers or visitors, but perhaps only 500 would be added to the User List for that target group’s campaign.

Note also that Google requires a minimum of 300 IDs in order for a User List to become active. You can associate one Google User List with more than one Optimove campaign in order to reach the 300-customer/visitor threshold, although, of course, all the associated Optimove campaigns will result in the single Google campaign run to that list.

### **Set up the Campaign in Google**
After the campaign is scheduled within Optimove, use the Google AdWords or DBM client to create the desired campaign for the User List populated by Optimove.
