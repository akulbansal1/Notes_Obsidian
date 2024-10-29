# <u>Week 2</u>
- ##### Scraping with Excel
	- Using Data > Query > From web and paste the URL
- ##### Scraping with Google Sheets
	- `IMPORTHTML(url,query,index)`
		- `query`: "list" or "table"
		- `index`: which table/list to scrape
- ##### BBC weather location service
	- refer to the `bbc_weather_location.py` file in `IITM Degree/TDS/` folder
- ##### Scraping IMDb using Browser JavaScript
	- run `document.querySelectorAll(".ipc-metadata-list-summary-item")` in the Console on website https://www.imdb.com/chart/top/
	- `$$(".ipc-metadata-list-summary-item").map(item => item.textContent)`
	- `$$(".ipc-metadata-list-summary-item").map(item => item.querySelector(".ipc-title__text").textContent)` will return an array with all the titles
	- `$$(".ipc-metadata-list-summary-item").map(item => [item.querySelector(".ipc-title-link-wrapper").href , item.querySelector(".ipc-title__text").textContent])` will return an array of each array containing the link to the movie and the movie title
	- `$$(".ipc-metadata-list-summary-item").map(item => [item.querySelector(".ipc-title-link-wrapper").href , item.querySelector(".ipc-title__text").textContent , item.querySelector(".cli-title-metadata-item:nth-child(1)").textContent])` will also include the year of the movie in each child array
	- to copy the entire data in JSON format to clipboard
		```javascript
		copy(
			$$(".ipc-metadata-list-summary-item").map(item => [
		    item.querySelector(".ipc-title-link-wrapper").href,
		    item.querySelector(".ipc-title__text").textContent,
		    item.querySelector(".cli-title-metadata-item:nth-child(1)").textContent,
		    item.querySelector(".cli-title-metadata-item:nth-child(2)").textContent,
		    item.querySelector(".cli-title-metadata-item:nth-child(3)")?.textContent,
		    item.querySelector(".ipc-rating-star--rating").textContent,
		    item.querySelector(".ipc-rating-star--voteCount").textContent
			])
		)
		```
		- can convert JSON to Excel format using convertor websites
- ##### Nominatim Open Street Maps
	- refer the `W2GA.py` file
- ##### Scraping PDFs from a URL

# <u>Week 3</u>
- ##### Excel functions
	- Use `TRIM()` function to remove whitespaces
	- 'Text to Column' feature under the Data tab to convert a column of text into more structured data
- ##### Data preparation in shell
	- fetch a file from Google Drive
	- Drive link: https://drive.google.com/file/d/1xLx-odohCtdPYbpOTui23upsCSzMBlpN/view
	```python
	!curl --location --continue-at - --output s-anand.net-May-2024.gz 'https://drive.google.com/uc?id=1xLx-odohCtdPYbpOTui23upsCSzMBlpN&export=download'
	
	!gzip --decompress s-anan.net-May-2024.gz
	
	!sed 's/\[\([^]]*\)\]/"\1"/g' s-anand.net-May-2024 > log.csv
	```
- ##### Data preparation in the editor
	- Change formatting in VS editor: Ctrl+Shift+P then type "Format Document"
	- Select all the instances of a word in VS editors: Ctrl+F then type the keyword then alt+enter
- ##### Cleaning data with Open Refine
	- [video](https://www.youtube.com/watch?v=zxEtfHseE84&ab_channel=IITMadras-B.S.DegreeProgramme)
- ##### Discover the data profile with Python
	```python
	from pandas_profiling import ProfileReport
	import pandas as pd
	
	prof = ProfileReport(df)
	prof.to_file('report.html')
	```

# <u>Week 4</u>
- ##### Regression with Excel
	- use the "regression" from Data Analysis Toolpak
- ##### Forecasting with Excel
	- `=FORECAST()` function uses linear regression
	- can also use `=TREND()` to forecast for multiple rows in one shot
	- `FORECAST.ETS()` for cyclical data
- ##### Outlier detection with Excel
	- calculate Quartile using `Quartile` and then using IQR, identify outliers
- ##### Data analysis in Python
	- use `parquet` files
		```python
		df.write_parquet('file.parquet')
		df = pd.read_parquet('file.parquet')
		```
	- can use `df.pivot_table(index, columns, values, aggfunc)` to create a pivot table from the dataframe.
- ##### Data analysis in Databases
	```python
	stats_connection = "mysql+pymysql://guest:relational@db.relational-data.org/stats"
	stats_connection = "mysql+pymysql://<username>:<password>@<hostname>/<database>"
	
	import pandas as pd
	import sqlalchemy as sa
	
	engine = sa.create_engine(stats_connection)
	pd.read_sql('SELECT COUNT(*) FROM posts', engine)
	```
- ##### DuckDB
	- allows you to read data directly from a file like you would from a database
		```python
		import duckdb
		
		delays = duckdb.query('''SELECT DEPARTURE_DELAY, COUNT(DISTINCT DISTANCE) FROM "2015_flights.parquet" GROUP BY DEPARTURE_DELAY ORDER BY DEPARTURE_DELAY''').df()
		```
	- cal also directly query pandas dataframe
		- useful in case any pandas function is extremely slow
		```python
		df = pd.read_parquet('2015_flights.parquet')
		delays = duckdb.sql('SELECT DEPARTURE_DELAY, COUNT(DISTINCT DISTANCE) FROM df GROUP BY DEPARTURE_DELAY ORDER BY DEPARTURE_DELAY').df()
		```
	- 