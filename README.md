# Data Science Hackathon
## Possible Social media Sources to scrape from:
* LinkedIn
* Twitter
* Facebook
* Instagram
## Obtaining list of startups
* From the website containing list of startups the JSON content was used to get a list of all the companies and their website.

## Choosing search engines:
* Google
* Bing

### Validating sources for extracting LinkedIn links:
Bing seemed to give better prioritized results for extracting the companies LinkedIn url. This could be because Bing is from Microsoft and LinkedIn is again a  subsidiary of Microsoft, the search results might be tuned better for LinkedIn.

<p align="center">
  <img src="https://github.com/paul2596/Data-Science-Hackathon/blob/main/img/linkedIn_bing_microsoft.jpg" width="650" alt="alt text">
</p>

## Extracting links and html content
* Forming search query: **({company name} + {website} + LinkedIn about page)**
  Example: **"Missionware PC https://www.missionware.com LinkedIn about page"**  
* The links were used and the html content from the companies LinkedIn profile was saved using the selenium library which automated the process.
* Each url was processed with an interval of 5 seconds to avoid triggering the human verification prompt.
* Source code:scrape_startups.ipynb,selenium_scrape_linkedin.ipynb

## Extracting required content from HTML 
* Once the html content was extracted for all the URLs. It was looped through and based on class name or id in the HTML tags the required text part was extracted into a pandas data frame.
* Source code:linkedin_data_from_html.ipynb
## The following data fields were extracted:
* Name
* Summary
* Location(from the top card)
* Employees on LinkedIn (social media presence)
* Followers count(social media presence)
* Overview 
* Founded
* Company size
* Industry
* Specialities
* Type
* Website
* Primary location


## Further to revalidate the extracted content and ensure data quality the following validations were performed

* The company name and domain names obtained from Greece startups database was compared with the ones on LinkedIn and a boolean column was added.

* If the primary location had 'GR' in it a boolean column is_greece was added.

<p align="center">
  <img src="https://github.com/paul2596/Data-Science-Hackathon/blob/main/img/linkedInValidation.jpg" width="950" alt="alt text">
</p>

## Options for companies that were not found
Lookup keywords on Twitter, Facebook and Job Portals to get an idea of what they actually do and relate the company to a particular industry.

