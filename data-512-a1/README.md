
# Goals
The goal of this repository is to construct, analyze, and publish a dataset of monthly traffic on English Wikipedia from January 1 2008 through August 30 2020.
We used 2 APIs, Jupyter Notebook, Python, pandas, matplotlib, numpy, and json. 

# Data Source
We acquired the data via the Wikimedia Foundation REST API.

- The Legacy Pagecounts API 

    - [documentation](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Legacy_Pagecounts)
    - [endpoint](https://wikimedia.org/api/rest_v1/#/Pagecounts_data_(legacy)/get_metrics_legacy_pagecounts_aggregate_project_access_site_granularity_start_end)
    
- The Pageviews API  
  - [documentation](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Pageviews)
  - [endpoint](https://wikimedia.org/api/rest_v1/#/Pageviews_data/get_metrics_pageviews_aggregate_project_access_agent_granularity_start_end)
    
# Final Data File
The final data file contains 151 rows (one per month) and 8 columns. 

The index are month dates. 

The columns are:
- year (int)
- month (int)
- pagecounts_all_view (float)
- pagecounts_desktop_view (float)
- pagecounts_mobile_view (float)
- pageviews_all_view (float)
- pageviews_desktop_view (float)
- pageviews_mobile_view (float)

# Special Considerations
The Pageview API excludes spiders/crawlers, while data from the Pagecounts API does not.

Pageviews API contains data from July 2015 through last month. 

Pageviews differentiates mobile data between website and app. 

Legacy Pagecounts API contains traffic data from December 2007 through July 2016.
