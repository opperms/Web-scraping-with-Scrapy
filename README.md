# Web-scraping-with-Scrapy

Getting Started - Cheat Sheet
In most cases use the commands below to get started:

- Clone this project: ``git clone https://github.com/python-scrapy-playbook/quotes-js-project.git``
- Create a Python Virtual Environment (not in the same directory as where the modules are, but one level above (see structure below): ``python -m venv venv``
- Activate the Python Virtual Environment: ``./venv/scripts/activate``
- Check that the latest release of pip is availible: ``python.exe -m pip install --upgrade pip``
- Install Scrapy using pip: ``pip install scrapy``
- Install Scrapy-Playwright: ``pip install scrapy-playwright``
- Check that Playwright in installed: ``playwright install``
- Listing the scrapy projects scrapy list
- Running the scrapy project: ``scrapy crawl quotes``

Here's a typical Scrapy project structure:

````bash
my_directory/
    myenv/               # virtual environment directory
    myproject/           # Scrapy project directory
        scrapy.cfg       # deploy configuration file
        myproject/       # project's Python module, you'll import your code from here
            __init__.py
            items.py     # project items file
            pipelines.py # project pipelines file
            settings.py  # project settings file
            spiders/     # a directory where you'll later put your spiders
                __init__.py
                spider1.py
                spider2.py
````

Add the following to the ``settings.py`` file:

````python
# settings.py
DOWNLOAD_HANDLERS = {
    "http": "scrapy_playwright.handler.ScrapyPlaywrightDownloadHandler",
    "https": "scrapy_playwright.handler.ScrapyPlaywrightDownloadHandler",
}
TWISTED_REACTOR = "twisted.internet.asyncioreactor.AsyncioSelectorReactor"``
