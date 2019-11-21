# sp500

#### Current List of S&P 500 companies retrieved from the Wikipedia  
#### Historical Lists of S&P 500 components since 1996

- `S&P 500 Historical Components & Changes(20-11-2019).csv`: contains historical S&P 500 index membership from 1996 til 20-11-2019.  Output from 'sp500_historical.ipynb' 
- `S&P 500 Historical Components & Changes.csv`: original historical S&P 500 index membership csv file.  Input to 'sp500_historical.ipynb'
- `sp500_changes_since_2019.csv`: S&P 500 composition changes since 2019.  Input to 'sp500_historical.ipynb'
- `sp500.csv`: composition of S&P 500.  Output from 'sp500.ipynb'.  Input to 'sp500_historical.ipynb'

- `sp500.ipynb`: retrieves current S&P 500 composition from Wikipedia and outputs 'sp500.csv'
- `sp500_historical.ipynb`: updates the original `S&P 500 Historical Components & Changes.csv` and outputs `S&P 500 Historical Components & Changes(MM-DD-YYYY).csv`
