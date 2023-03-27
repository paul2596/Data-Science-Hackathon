# Data Science Hackathon
## Possible Social media Sources to scrape from:
* LinkedIn
* Twitter
* Facebook
* Instagram

## Choosing search engines:
* Google
* Bing
* Duck duck go

### Validating sources for extracting LinkedIn links:
Bing seemed to give better prioritized results for extracting the companies LinkedIn url. This could be because Bing is from Microsoft and LinkedIn is a subsidiary of Microsoft, the search results might be tuned better for LinkedIn.

<p align="center">
  <img src="https://github.com/paul2596/Data-Science-Hackathon/blob/main/img/linkedIn_bing_microsoft.jpg" width="650" alt="alt text">
</p>

Once the links were extracted we got the html content from the companies LinkedIn profile using the selenium library to automate the process.
Each url was processed with an interval of 5 seconds to avoid triggering the human verification prompt.

Once all the html content was extracted for all the URLs. It was looped through and based on class name or I'd in the HTML tags the required text part was extracted into pandas data frame.

## The following data fields were extracted:
* Name
* Summary
* Location(from the top card)
* Employees on LinkedIn (social media presence)
* Followers count(social media presence)
* Overview 
* Company size
* Industry
* Specialities
* Type
* Website
* Primary location


## Further to revalidate the extracted content and ensure data quality the following validations were performed.

* The company name and domain names obtained from Greece startups database was compared with the ones on LinkedIn and a boolean column was added.

* If the primary location had 'GR' in it a boolean column is_greece was added.

<p align="center">
  <img src="https://github.com/paul2596/Data-Science-Hackathon/blob/main/img/linkedInValidation.jpg" width="950" alt="alt text">
</p>

## Options for companies that were not found.
Lookup keywords on Twitter, Facebook and Job Portals to get an idea of what they actually do and relate the company to a particular industry.

