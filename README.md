# Customer-Activity-Analysis
One import activity for a data analyst/ Engineer is to analyse or track the activity of the customers in the client website. This analysis can unearth the customer motivations which can add further business values to the client. 
In this project I analyse the behavour of the customer on a specific client website. The input dataset was avalable in a google sheet and the expected output should be in json format. The json format helps the frontend developers to display the output.
I was doing analysis for the following objectives: (**For data security reasons some of the varible names are abstructed**)
1. user count by type dev***_clas*
2. user count by each user's first (min date****) non-null om_so*rce . If the user journey contains no data for om_so*rce relabel the null value as “ no_om_so*rce ”
3. No of users had session durations of <=5 Seconds
        a. no of session journeys started on page_type=sear**_page
        b. no of session journeys ended on page_type=apart**nt_view
4. No of users journeys started on page_type=sear**_page and any point after in their user journey visited page_type=apart**nt_view       
5. No of users at any point in their user journey executed an event_type = ‘click_****-now’
6. No of users who started on page_type = sear**_page executed an event_type = ‘request_draft-crea**d’
7. No of users set a price filter above 1200 EUR and how many set a price filter below 1200 EUR (e.g {"event_c***ent":{"price":1200, “currency":"EUR”}}). If the
   currency is not EUR you can ignore that session.
8. No of users contain at least one re***st_id . (e.g {"event_content":{},"page":{"re***st_id":"1***********7d140"}}. If a session contains more than one re***st_id count that as only one.

**Below are the description of fields**


| Field         | Description                                                   | 
| ------------- |:-----------------------------------------------------:| 
| date****      | The timestamp of when the event happened on the site  |
| se**ion_id    | Unique id assigned to a user based on their cookie    | 
| is_i**rnal_ip | Boolean to denote whether the IP address is internal  |  
| pag***ype     | Our platform has many pages such as the homepage, search page, apartment page, etc. The pag***ype helps you determine on which page the event occurred.        |
|even***ype      | The action or event that the user performed on the site |
| par**s        | JSON string of page variables (e.g filters selected, page info, etc) |
| tes***roup   |  Used for AB tests. A JSON string of key value pairs for each test currently running {‘tes****y’: ‘tes***roup’} |
| o***ource    | OM refers to online marketing. We use many different marketing channels to drive traffic to our site. The value here corresponds to which channel the user came                  from. (Note. A single session can have multiple o***ource if for example the user interacts with another ad and comes back to our site within the same session.                  Blank o***ource means that the user came to our site organically and did not interact with an ad. |
| devic***lass | The type of device the user is on (e.g phone, table, desktop) |
| env          |   We have both a production and development environment. Production is our customer facing site and development is used internally for tracking on feature branches.


