## Objective:
Write an application that combines the data in the local company database with an external API.

## Requirements:

The app should be able to run on a system will limited resources. Do not read all the data in at one
time. 

## Data:

1. Local Database running PostgreSQL provided via a docker container. 
Which will contain the following customer data tables:
* customers
* stores

2. The External API: 

swagger doc: https://geo.fcc.gov/api/census/#!/block/get_block_find
example api call: https://geo.fcc.gov/api/census/area?lat=37.299590&lon=-76.742290&format=json


Outcome:

1. Customers and stores are updated with the following information
blockID or block fips id, state_fips, state code and block population.

2. A report is generated that lists the number of customer's per store blockID in a csv file.
the columns shoul be:
StoreName, BlockID, customerCount

3. The report should be uploaded to a s3 location specified by the person running the app at run time. Take care to
avoid leaking aws credentials.

4. The user will need to provide AWS credentials in a secure manner. 

