# Customer-Activity-Analysis
One import activity for a data analyst/ Engineer is to analyse or track the activity of the customers on the client website. This analysis can unearth the customer motivations which can add further business values to the client. In this project, I analyse the behaviour of the customer on a specific client website. The input dataset was available in a google sheet and the expected output should be in JSON format. The JSON format helps the frontend developers to display the output. I was analyzing the following objectives: 
1. user count by type device_class
2. user count by each user's first (min datetime) non-null om_source . If the user journey contains no data for om_so*rce relabel the null value as “ no_om_source ”
3. No of users had session durations of <=5 Seconds
        a. no of session journeys started on page_type=search_page
        b. no of session journeys ended on page_type=apartment_view
4. No of users journeys started on page_type=search_page and any point after in their user journey visited page_type=apart**nt_view       
5. No of users at any point in their user journey executed an event_type = ‘click_book-now’
6. No of users who started on page_type = search_page executed an event_type = ‘request_draft-created’
7. No of users set a price filter above 1200 EUR and how many set a price filter below 1200 EUR (e.g {"event_content":{"price":1200, “currency":"EUR”}}). If the
   currency is not EUR you can ignore that session.
8. No of users contain at least one request_id . (e.g {"event_content":{},"page":{"request_id":"1***********7d140"}}. If a session contains more than one request_id count that as only one.

**Below are the description of fields**


| Field         | Description                                                   | 
| ------------- |:-----------------------------------------------------:| 
| datetime      | The timestamp of when the event happened on the site  |
| session_id    | Unique id assigned to a user based on their cookie    | 
| is_internal_ip | Boolean to denote whether the IP address is internal  |  
| page_type     | Our platform has many pages such as the homepage, search page, apartment page, etc. The page_type helps you determine on which page the event occurred.        |
|event_type     | The action or event that the user performed on the site |
| params       | JSON string of page variables (e.g filters selected, page info, etc) |
| test_groups   |  Used for AB tests. A JSON string of key value pairs for each test currently running {‘test_key’: ‘test_groups’} |
| om_source    | OM refers to online marketing. We use many different marketing channels to drive traffic to our site. The value here corresponds to which channel the user came                  from. (Note. A single session can have multiple om_sources if for example the user interacts with another ad and comes back to our site within the same session.                  Blank om_sources means that the user came to our site organically and did not interact with an ad. |
| device_class | The type of device the user is on (e.g phone, table, desktop) |
| env          |   We have both a production and development environment. Production is our customer facing site and development is used internally for tracking on feature branches.


