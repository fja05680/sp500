# sp500

##### Current List of S&P 500 companies retrieved from the Wikipedia: `sp500.csv` 
##### Historical Lists of S&P 500 components since 1996: `S&P 500 Historical Components & Changes(MM-DD-YYYY).csv`
##### Example code to retrieve a snapshot of the S&P 500 components on a certain date: `sp500_by_date.ipynb`

### Description of Files

- `S&P 500 Historical Components & Changes(MM-DD-YYYY).csv`: contains historical S&P 500 index membership from 1996 til MM-DD-YYYY.  Output from 'sp500_historical.ipynb' 
- `S&P 500 Historical Components & Changes.csv`: original historical S&P 500 index membership csv file.  Input to 'sp500_historical.ipynb'
- `sp500_changes_since_2019.csv`: S&P 500 composition changes since 2019.  Input to 'sp500_historical.ipynb'
- `sp500.csv`: composition of S&P 500.  Output from 'sp500.ipynb'.  Input to 'sp500_historical.ipynb'

- `sp500.ipynb`: retrieves current S&P 500 composition from Wikipedia and outputs 'sp500.csv'
- `sp500_historical.ipynb`: updates the original `S&P 500 Historical Components & Changes.csv` and outputs `S&P 500 Historical Components & Changes(MM-DD-YYYY).csv`
- `sp500_by_date.ipynb`: example demonstrates how to retrieve a snap shot of the S&P 500 components on a certain date.  Also lists the symbols that have been added and removed from that date to the present.
- `PIT to Ticker Delta.ipynb`: Convert Point in Time list of Tickers in the S&P 500 to Tickers first and last date in the S&P 500 over the history. Have some instances where tickers come and go multiple times. Data integrity is based on the base ticker list.  Outputs `sp500_ticker_start_end.csv`.

### Notes

(1) I recommend that you get a copy of `Trading Evolved` by Andreas Clenow.  He explains the complexity of backtesting equities.  I got my original list as a download associated with the book.  `S&P 500 Historical Components & Changes.csv` is the original file that I got from him that runs from 1996 to 2019.  Every couple of months, I use the S&P 500 Wikipedia page and update `sp500_changes_since_2019.csv` with any changes that have occurred to the index.  The first thing I do when I update is to compare my latest entry to current Wikipedia page for S&P 500. I see what the differences are.  Wikipedia shows "Selected Changes" not all changes.  The changes section is helpful but not always complete. I have to Google search to get exact dates and the story of what happened. You can't reconstruct the past with only the Wikipedia changes mentioned.  The code I've written merges the original file with the index changes and outputs an updated csv file, e.g. `S&P 500 Historical Components & Changes(MM-DD-YYYY).csv`.  (It also does some data cleaning of the original).

(2) The ticker names are correct on any day you pick from the csv file.  If they are missing later, you can assume they were removed from the index and you sell that position.  Even if the company was not removed but the symbol changed, you sell.  Your algorithm will pick up the new name if it meets your criteria.  So you don't actually need the company name or any other information linking the symbols.

(3) Andreas is a professional, so I trust that his information is accurate.  In the book, he uses Norgate Data for his stock timeseries data.  Another cheaper alternative is eoddata.  You need this for the delisted and changed symbols in the S&P 500 history.  Yahoo Finance only keeps current stock history.  I'm grateful that they provide this for free.  But if you want to backtest stocks, you are going to need to purchase data.  

(4) I feel confident that the Wikipedia has the correct current members. I make sure my final list matches the Wikipedia. I'm also very careful to make the changes file `sp500_changes_since_2019.csv` as accurate as possible.

(5) It's generally not the case that there are exactly 500 stocks in the S&P 500. As of 05-05-2021, there are 505. Sometimes there may be a few less than 500 because of the timing of additions/removals to/from the index. There are 487 symbols in the first row. This is part of the original list I got from Andreas Clenow with only data cleaning and removal of duplicates (which I verified doesn't remove any unique symbols). I feel like there may be some missing symbols for those first 5 years, but I have no way to independently check it. The number of symbols seems to slowly increase moving forward in time. On 2001-01-16 there are 494 symbols and it never falls below that number again. If this is a concern (not close enough to 500), perhaps just don't use the first ~5 years of data. That still gives you over 20 years beginning in 2001.

Here are the some statistics for all the rows as of 05-05-2021.  
```
count  2595    (number of rows)  
mean   496.44  (number of symbols)  
std    5.04  
min    487  
25%    494  
50%    497  
75%    499  
max    507
```
