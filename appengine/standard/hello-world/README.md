## Launch serverless : appengine

``
gcloud app deploy --version 1
``

``
gcloud app deploy --version 2
``



## Migrate traffic back to Version 1

Check the box next to Version 1
At the top menu, click on 'Migrate Traffic'
When complete, verify webpage for Version 1 is displayed

### Command line use:
- To migrate immediately, run the following command:

``
    gcloud app services set-traffic [MY_SERVICE] --splits [MY_VERSION]=1
``

- To migrate gradually, run the following command:

``
    gcloud app services set-traffic [MY_SERVICE] --splits [MY_VERSION]=1 --migrate
``


## Split Traffic to both Versions

At the top menu, click on 'Split Traffic'
Split traffic by > Random
Traffic allocation
Version 2 > Allocation 50%
Version 1 > Allocation 50%
Click Save

### Commanline use:
- To split traffic by using either an IP address or HTTP cookie: 

``
    gcloud app services set-traffic [MY_SERVICE] --splits [MY_VERSION1]=[VERSION1_WEIGHT],[MY_VERSION2]=[VERSION2_WEIGHT] --split-by [IP_OR_COOKIE]
``


## Cleanup to not be charged any cost
``` Settings > Disable application ```
- You will be prompted to type in your AppID 
- Type it in the box provided
- Click Disable

`` Click on the link to your Cloud Storage bucket ``

- Make sure there are no files in this bucket 
- Delete the bucket named staging.PROJECT_ID.appspot.com 
- Delete the bucket named us.artifacts.PROJECT_ID.appspot.com 




## References remaining:

- Storing and Retrieving Data
- Adding Firebase to your Web Service
- Authenticating users with Firebase
- Personalizing Data for Authenticated Users

- Test and deploy your app