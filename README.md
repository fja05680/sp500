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

### Notes

(1) I recommend that you get a copy of `Trading Evolved` by Andreas Clenow.  He explains the complexity of backtesting equities.  I got my original list as a download associated with the book.  `S&P 500 Historical Components & Changes.csv` is the original file that I got from him that runs from 1996 to 2019.  Every couple of months, I use the S&P 500 Wikipedia page and update `sp500_changes_since_2019.csv` with any changes that have occurred to the index.  The first thing I do when I update is to compare my latest entry to current Wikipedia page for S&P 500. I see what the differences are.  Wikipedia shows "Selected Changes" not all changes.  The changes section is helpful but not always complete. I have to Google search to get exact dates and the story of what happened. You can't reconstruct the past with only the Wikipedia changes mentioned.  The code I've written merges the original file with the index changes and outputs an updated csv file, e.g. `S&P 500 Historical Components & Changes(MM-DD-YYYY).csv`.  (It also does some data cleaning of the original).


(2) The ticker names are correct on any day you pick from the csv file.  If they are missing later, you can assume they were removed from the index and you sell that position.  Even if the company was not removed but the symbol changed, you sell.  Your algorithm will pick up the new name if it meets your criteria.  So you don't actually need the company name or any other information linking the symbols.

(3) Andreas is a professional, so I trust that his information is accurate.  In the book, he uses Norgate Data for his stock timeseries data.  Another cheaper alternative is eoddata.  You need this for the delisted and changed symbols in the S&P 500 history.  Yahoo Finance only keeps current stock history.  I'm grateful that they provide this for free.  But if you want to backtest stocks, you are going to need to purchase data.  

(4) I feel confident that the Wikipedia has the correct current members. I make sure my final list matches the Wikipedia. I'm also very careful to make the changes file `sp500_changes_since_2019.csv` as accurate as possible.
