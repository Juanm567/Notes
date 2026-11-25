# Scrapy

 **Item:** Container defines the structure of the data that you want to collect, 

  * Python mapping -> would assign values like with a dictionary
  * provides features such as 

    * validation
    * serialization
  * To use: 

    1. Create class that inherits from 'scrapy.Item'
    2. Define fields that you want to scrape as instances of 'scrapy.Field'
    * Dont forget to 'import scrapy'



**Spider :** Python class responsible for visiting websites, extracting information, and following links to other pages

## Steps to set up the spider inside of respective folder

  1. 'cd books'
  2. scrapy genspider book https://books.toscrape.com/	
  3. By passing a spider name and the target URL to genspider, Scrapy creates a new file in the spiders/ directory of your project
  * Spider has a name and needs

      * Where to start scraping
      * How to parse the response

        * ' start_urls' is a list of strings that contains only one URL in your case, but could contain more
        * The .parse() method of a Spider is a callback method that Scrapy calls with the downloaded response object for each URL.

        * Callback method: function that you pass as an argument to another function. The receiving function can then call the callback at a later point, often as a response to an event or after completing a task.
    * Anchor element (<'a'>): HTML element that creates clickable links.

      * href → URL the link points to.
      * ::attr(href) → Extracts the URL.
      * ::attr(title) → Extracts the title attribute.
      * ::text → Extracts the visible text.
      * '>' → Selects a direct child element.

'Yield': Python keyword that produces a value and pauses a generator function.

  * Unlike `return`, `yield` does not terminate the function.
  * &#x20;When resumed, execution continues from the line after `yield`.
  * Local variables and their values are preserved.
  * A function containing `yield` is called a \*\*generator function\*\*.
  * &#x20;`function\_name()` → Creates a new generator object.
  * &#x20;`next(gen)` → Executes until the next `yield`.
  * &#x20;Calling `function\_name()` again creates a NEW generator, not resumes the previous one.
  * &#x20;`for` loops automatically call `next()` until the generator finishes.
  * &#x20;In Scrapy, `yield` passes scraped items or requests to the framework, which handles iteration automatically.



&#x09;To run spider:

      * 'scrapy crawl book' -> finds a spider named 'book' and starts the crawling process
      * remember you must run this from the project root containing scrapy.cfg
      * web crawling

&#x09;	Web crawling means to systematically browse the Web to index and collect information. The primary function of a web crawler is to follow links on web pages to discover new content and gather data. In the context of web scraping, a crawler can navigate through different pages of a website, extract 		relevant information, and store it for further use.

* Do not forget to run spider with the command "scrapy crawl 'spider_name'"

# MongoDB
-  MongoDB is a non-relational, document-oriented database
  that organizes data into collections of BSON documents.
 -  Set up MongoDB(Atlas) which allows users to store and access data remotely without mantaining their own database servers

### MongoDB hierarchy
```text
Cluster
 └── Database
      └── Collection
           └── Document
                └── Fields
```
## What is a cluster
- Group of servers that store process and manage data
  - Benefits : Reliability, availability and scalibilty

- Replication: Stores copies of the same data across
  multiple servers.
    * Improves reliability and availability.
    * Requires additional storage space.

* Sharding: Distributes portions of data across servers.
    * Improves scalability and distributes workload.
    * Without replication, server failure can make
      portions of the data unavailable.

* MongoDB supports both replication and sharding.
  The free Atlas cluster uses replication.
### Cloud infrastructure and MongoDB (Atlas)
- MongoDB (Atlas) uses servers built from infrasture provided by Google, Amazon, Microsoft which are in physical datacenters