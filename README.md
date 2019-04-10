# Scrubbing_Cars-dot-com
Another Scraping Script with Selenium Chromedriver




#####################################################################################
# ScrapeScript_cars(dot)com_v1.py
#
# Script for scraping a Consumer Reviews page on https://www.cars.com/ using...
# Homepage URL: https://www.cars.com/
# Tools: Selenium, ChromeDriver
# Data Organizer: Pandas
#
# Version: 1
# Date Created: 01/31/2019
# Last Modified: 02/04/2019
#####################################################################################


# In[119]:


##### READ ME #######################################################################
#
# This script is able to scrape the Consumer Reviews for a vehicle on:
# https://www.cars.com/
#
# This script's code should only be executed at portions at a time due to
# ChromeDriver being unable to open the given webpage all the time.
# Please do not run this script as an executable / as a whole.
#
# Before running this script:
# 1. Change the values of the global variables in the "GLOBAL VARIABLES" section
#    as necessary. Please read the notes attached to each when changing the value.
# 2. Reminder: If you change the value of any of the global variables, please
#    re-run the "GLOBAL VARIABLES" section before executing any code that uses
#    the global variable you changed or updated.
# 3. cars.com can only show a maximum of 250 reviews per page. If there are more
#    than 250 reviews for a vehicle, there will be more than one page. This script
#    is only capable of scraping a single page at a time, so please manually change
#    the URL with the next page (after scraping the first page) and re-run the
#    script to scrape the next page separately.
#
# When running this script:
# 1. Messages will print out to the terminal to indicate where the code is
#    currently at during execution.
# 2. If the webpage does not load when ChromeDriver starts, please manually
#    reload the page in the same window until the webpage loads.
# 3. Please allow the webpage to fully load before moving on.
# 4. Please do not click on any buttons that read "Show Full Review".
#    Make sure all reviews have not been expanded by the user.
# 5. Please make sure the browser window displays the top of the page before
#    running the code that expands all reviews.
#
# NOTES:
# 1. If an error occurs during the data extraction process for one post,
#    the post's row will contain empty data on the Pandas data frame and output.
# 2. When extracing post data for one post, an IndexError message may appear to
#    indicate that the post in question did not include all 4 optional fields
#    towards the end of the review. These fields will show as blank strings in
#    the Pandas data frame and output.
#
##### CODE OVERVIEW #################################################################
#
# 1. Start up ChromeDriver and open the given URL on https://www.cars.com/.
# 2. Get all Post IDs associated with a review on the page.
# 3. Expand all reviews by clicking on the "Show Full Review" button on each post.
# 4. Extract the post data for each Post ID and parse certain fields as necessary.
# 5. Add the post's data to the global list (all_post_data) containing the data
#    for all posts.
# 6. Put the data in all_post_data into a Pandas data frame.
# 7. Export the data frame to a .csv file.
#
#####################################################################################


