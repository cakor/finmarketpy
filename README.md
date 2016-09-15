# finmarketpy (formally pythalesians)

finmarketpy is a Python based library that enables you to analyze market data and also to backtest trading strategies using
a simple to use API, which has prebuilt templates for you to define backtest. Included in the library

* Prebuilt templates for backtesting trading strategies
* Display historical returns for trading strategies
* Investigate seasonality of trading strategies
* Conduct market event studies around data events
* In built calculator for risk weighting using volatility targeting
* Written in object orientated way to make code more reusable

# Merging with pythalesians
I had previously written the open source PyThalesians financial library (which has been merged with this - so can focus on maintaining
one set of libraries). This new finmarketpy library has 
* Similar functionality to the trading part of pythalesians
* rewritten the API to make it much cleaner and easier to use, as well as having many 
new features. 
* finmarketpy requires the libraries, which I've written chartpy (for charts) and findatapy (for loading market data) to function
* By splitting up into smaller more specialised libraries, it should make it easier for contributors
* Using findatapy, you can download market data easily from Bloomberg, Quandl, Yahoo etc
* Using chartpy, you can choose to have results displayed in matplotlib, plotly or bokeh by changing single keyword!

Points to note:
* Please bear in mind at present finmarketpy is currently a highly experimental alpha project and isn't yet fully 
documented
* Uses Apache 2.0 licence

# Gallery

Calculate the cumulative returns of a trading strategy historically (see examples/tradingmodelfxtrend_example.py)

<img src="https://github.com/cuemacro/finmarketpy/blob/master/finmarketpy/examples/gallery/fx-trend-cumulative.png?raw=true" width="750"/>

Plot the leverage of the strategy over time

<img src="https://github.com/cuemacro/finmarketpy/blob/master/finmarketpy/examples/gallery/fx-trend-leverage.png?raw=true" width="750"/>

Plot the individual trade returns

<img src="https://github.com/cuemacro/finmarketpy/blob/master/finmarketpy/examples/gallery/fx-trend-trade-returns.png?raw=true" width="750"/>

Calculate seasonality of any asset: here we show gold and FX volatility seasonality (see examples/seasonality_examples.py)

<img src="https://github.com/cuemacro/finmarketpy/blob/master/finmarketpy/examples/gallery/gold-seasonality.png?raw=true" width="750"/>

<img src="https://github.com/cuemacro/finmarketpy/blob/master/finmarketpy/examples/gallery/fx-vol-seasonality.png?raw=true" width="750"/>

Calculate event study around events for asset (see examples/events_examples.py)

<img src="https://github.com/cuemacro/finmarketpy/blob/master/finmarketpy/examples/gallery/usdjpy-nfp.png?raw=true" width="750"/>


# Requirements

Major requirements
* Required: Python 3.4, 3.5
* Required: pandas 0.18, numpy etc.
* Required: findatapy for downloading market data (https://github.com/cuemacro/findatapy)
* Required: chartpy for funky interactive plots (https://github.com/cuemacro/chartpy)
* Recommended: multiprocessor_on_dill because standard multiprocessing library pickle causes issues 
(from https://github.com/sixty-north/multiprocessing_on_dill)

# Installation

You can install the library using the below (better to get the newest version from repo, as opposed to releases). After installation:
* Make sure you edit the MarketConstants file

```
pip install git+https://github.com/cuemacro/finmarketpy.git
```

But beforehand please make sure you have already installed both chartpy, findatapy and any other dependencies

```
pip install git+https://github.com/cuemacro/chartpy.git
pip install git+https://github.com/cuemacro/findatapy.git
```

# finmarketpy examples

In finmarketpy/examples you will find several examples, including some simple trading models

# Release Notes

* 0.11 - finmarketpy
* First prerelease version 

# Coding log

# finmarketpy log

* 15 Sep 2016 - Merged finmarketpy and pythalesians fully
* 12 Sep 2016 - Fixed issue with TradeAnalysis (method names)
* 02 Sep 2016 - Fixed issue with external dataframe eco events, added event study example
* 01 Sep 2016 - Added seasonality example for FX vol
* 22 Aug 2016 - Fixed boot issue and added credentials
* 17 Aug 2016 - Uploaded first code

# pythalesians log

* 03 Aug 2016 - Fixed missing conf files
* 02 Aug 2016 - Changed default Plotly background color and fixed constants issue with AdapterTemplate
* 01 Aug 2016 - Renamed pythalesians_graphics as chartesians (preparing eventual spinout)
* 29 Jul 2016 - Created Jupyter notebook plot_market_data for plotting with multiple libraries, also fixed Bokeh sizing issue,
refactored library, spinning out chart functionality into pythalesians_graphics
* 28 Jul 2016 - Fixed issue with multiple fields returned by Quandl, added Quandl downloading example
* 26 Jul 2016 - Added more support for Plotly charts, added surface vol Plotly example
* 21 Jul 2016 - Refactor StrategyTemplate graph plotting functions
* 20 Jul 2016 - Return of figure handle for AdapterPyThalesians
* 08 Jun 2016 - Fix kurtosis issue, refactored vol scaling in CashBasktest, added resample wrapper in TimeSeriesFilter
* 03 Jun 2016 - Speed up CashBacktest (construct_strategy method)  
* 02 Jun 2016 - Fixed missing StrategyTemplate file in installation, added auto-detection of path 
to simplify installation and added methods for converting between pandas and bcolz
* 31 May 2016 - Got rid of deprecated Pandas methods in TechIndicator
* 27 May 2016 - Added ability to plot strategy signal at point in time
* 19 May 2016 - Updated Quandl wrapper to use new Quandl API
* 02 May 2016 - Tidied up BacktestRequest, added SPX seasonality example
* 28 Apr 2016 - Updated cashbacktest (for Pandas 0.18)
* 21 Apr 2016 - Got rid of deprecated Pandas methods in EventStudy
* 18 Apr 2016 - Fixed some incompatibility issues with Pandas 0.18
* 06 Apr 2016 - Added more trade statistics output
* 01 Apr 2016 - Speeded up joining operations, noticeable when fetching high freq time series
* 21 Mar 2016 - Added IPython notebook to demonstrate how to backtest simple FX trend following trading strategy
* 19 Mar 2016 - Tested with Python 3.5 64 bit (Anaconda 2.5 on Windows 10)
* 17 Mar 2016 - Refactored some of graph/time series functions and StrategyTemplate
* 11 Mar 2016 - Fixed warnings in matplotlib 1.5
* 09 Mar 2016 - Added more TradeAnalysis features (for sensitivity analysis of trading strategies)
* 01 Mar 2016 - Added IPython notebook to demonstrate how to download market data and plot
* 27 Feb 2016 - Fixed total returns FX example
* 20 Feb 2016 - Added more parameters for StrategyTemplate
* 13 Feb 2016 - Edited time series filter methods
* 11 Feb 2016 - Added example to plot BoJ interventions against USDJPY spot
* 10 Feb 2016 - Updated project description
* 01 Feb 2016 - Added LightEventsFactory to make it easier to deal with econ data events (stored as HDF5 files)
* 20 Jan 2016 - Added kurtosis measure for trading strategy results, fixed Quandl issue
* 19 Jan 2016 - Changed examples folder name
* 15 Jan 2016 - Added risk on/off FX correlation example
* 05 Jan 2016 - Added total return (spot) indices construction for FX and example
* 26 Dec 2015 - Fixed problem with econ data downloaders
* 24 Dec 2015 - Added datafactory templates for creating custom indicators
* 19 Dec 2015 - Refactored Dukascopy downloader
* 10 Dec 2015 - Various bug fixes
* 22 Nov 2015 - Increased vol targeting features for doing backtesting
* 07 Nov 2015 - Added feature to download tick data from Bloomberg (with example)
* 05 Nov 2015 - Added intraday event study class (and example)
* 02 Nov 2015 - Added easy wrapper for doing rolling correlations (and example)
* 28 Oct 2015 - Added more sensitivity analysis for trading strategies
* 26 Oct 2015 - Various bug fixes for Bloomberg Open API downloader
* 14 Oct 2015 - Added capability to do parallel downloading of market data (thread/multiprocessing library), with an 
example for benchmarking and bug fixes for Bloomberg downloader
* 25 Sep 2015 - Refactored examples into different folders / more seasonality examples
* 19 Sep 2015 - Added support for Plotly choropleth map plots & easy downloading of economic data via FRED/Bloomberg/Quandl
* 12 Sep 2015 - Added basic support for PyFolio for statistical analysis of strategies
* 04 Sep 2015 - Added StrategyTemplate for backtesting (with example) & bug fixes
* 21 Aug 2015 - Added stacked charts (with matplotlib & bokeh) & several bug fixes
* 15 Aug 2015 - Added bar charts (with matplotlib & bokeh) & added more time series filter functions
* 09 Aug 2015 - Improved Bokeh support
* 07 Aug 2015 - Added Plotly support (via Jorge Santos Cufflinks wrapper)
* 04 Aug 2015 - Added ability to download from FRED and example for downloading from FRED.
* 29 Jul 2015 - Added backtesting functions (including simple FX trend following strategy) and various bug fixes/comments.
* 24 Jul 2015 - Added functions for doing simple seasonality studies and added examples.
* 17 Jul 2015 - Created example to show how to use technical indicators.
* 13 Jul 2015 - Changed location of conf, renamed examples folder to pythalesians_examples. Can now be installed using setup.py.
* 10 Jul 2015 - Added ability to download Dukascopy FX tick data (data is free for personal use - check Dukascopy terms & conditions). Note that past month of data is generally not made available by Dukascopy

End of note


End of note
