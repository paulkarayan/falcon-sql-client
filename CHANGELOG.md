# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/en/1.0.0/)
and this project adheres to [Semantic Versioning](http://semver.org/spec/v2.0.0.html).


## [Unreleased]

### Added

### Changed

### Deprecated

### Removed

### Fixed

### Security


## [3.0.1] - 2018-08-06

### Fixed
* Scheduler: Upload grid metadata as required by Chart Studio  (#504)
* OnPrem: Fixed /external-data-connector page not accessible in private mode
  (#505)


## [3.0.0] - 2018-07-27

### Added
* Added UI to show scheduled queries (#472)
* Added UI to create, update and delete scheduled queries (#476)
* Support cron rules to schedule queries (#488)
* Added UI to name scheduled queries (#500)

### Changed
* The refresh interval of scheduled queries created in previous versions of
  Falcon is now converted into one of the following: every minute, every 5
  minutes, hourly, daily and weekly (#488)

### Removed
* Removed the chart editor and the export tab when running onprem mode (#496)

### Fixed
* MSSQL: Fixed #299, #409 and #462 (#464)

### Security
* Mitigated clickjacking by setting `X-Frame-Options: DENY` (#489)


## [2.8.0] - 2018-06-07

### Fixed
* Fixed query panel for non-sql connectors (#451)
* Fixed build failure with dtrace-provider (#421)
* Fixed broken oauth redirection in web app (#260)

### Security
* Disabled nodeIntegration (#453)
* Ensured new windows are created using `shell.openExternal` (#453)


## [2.7.0] - 2018-05-28

### Added
* Connector for Oracle databases (#437)
* Backend: Added API for creating a grid to store results from scheduled queries (#444)

### Changed
* UI: Added a vertical scrollbar to the database view
* UI: Don't hide the code editor when the chart editor opens (#445)
* Log: Reduced verbosity

### Fixed
* Backend: Fixed error message on failed connection

### Security
* Upgraded to Electron v2.0.1 (and Node v8)
* Prevent navigation on drag'n'drop (#436)


## [2.6.0] - 2018-04-13

### Added
* Connector to AWS Athena service (#352 contributed by Shannon Lal @shannonlal)
* Connector to query CSV files (via URL or drag'n'drop) (#375 and #385)
* New chart editor based on Plotly React Component Suite (#405)
* New code editor, resizeable and with improved performance (#411)
* New table view with row filters (#393)
* Test UI using jest and enzyme

### Changed
* ElasticSearch: Use mocked servers for testing
* ElasticSearch: Run tests against elasticsearch v2 and v5
* Query: Show query times (#358 contributed by Álvaro Abella Bascarán, @alvaroabascar)
* Query: Improved error displays (#394)

### Fixed
* CodeEditor: Fixed initial query (#371)
* ElasticSearch: Fixed connection to an elasticsearch server behind nginx (#377)
* Query: Prevent the code editor from opening before a table has been selected (#379)
* Test: Improved logging of backend failures


## [2.5.0] - 2018-01-19

### Added
* Connector for https://data.world

### Changed
* test: implemented mock connectors
* test: updated DB2, Impala and Spark sample servers
* Enabled asar in the installers for Mac and Linux

### Deprecated
* test: DB2 and Spark sample servers will be turned off in the near future.
  Please, instead, use the docker containers:
  - quay.io/plotly/falcon-test-db2
  - quay.io/plotly/falcon-test-spark


## [2.4.0] - 2017-12-15

### Added
* CHANGELOG.md
* Windows installer
* Mac installer

### Changed
* Reduced app size
* Desktop app can run without logging into Plotly
* Do not download fonts

### Removed
* OnPrem: removed `Download CSV`

### Fixed
* CodeEditor: Restored functionality to autocomplete keywords and table names
* CodeEditor: Fixed issue with the button `Run` becoming unclickable or hidden
* DB2: Fixed error with Falcon being unable to locate the ibm_db driver in Mac
* OnPrem: Fixed multiple OAuth issues
* OnPrem: Fixed export link
* Postgres: Fixed table preview to show tables in all the schemas
* Postgres: Accept schema names and quoted identifiers
* Redshift: Fixed table preview to show tables in all the schemas
* Redshift: Accept schema names and quoted identifiers
* Sqlite: Fixed the file selector in Windows and Linux
* Sqlite: Fixed the schemas overview


## [2.3.2] - 2017-11-01

### Added
* Connector for Apache Impala.

### Changed
* Rebranded Plotly Database Connector to Falcon SQL Client
* Do not create SSL certificates if user is not logged into Plotly

### Fixed
* DB2: build ibm_db driver against electron
* oauth: login redirection


## [2.3] - 2017-10-11

### Added
* Connectors for Hive via SparkSQL and IBM DB2.
* Public sample datastores for trying out the app with no fuss.
* All requests are now authenticated by default. This allows this app to be run
  as a public server while still securely ferrying data between plot.ly and the
  connected datastores. Authentication is enabled by default, but can be turned
  off using AUTH_ENABLED setting.
* Restricted access through OAuth. Access to the app running as a server can be
  restricted with an ALLOWED_USERS setting.
* Standalone, interactive SQL Editor. The editor features data preview,
  typeahead, database schema previews, and inline data visualization.
* Drag-and-drop chart GUI for creating and exporting plotly.js charts.
* Optionally export charts and CSV data to plot.ly. Plot.ly has further editing,
  export, and online sharing options.
* CSV download of data to desktop.
* PNG download of charts to desktop.


## [2.1.0] - 2017-08-24

### Changed
* Reorganized app with horizontal tabs to eliminate need for vertical scroll
* Organized header links into an upper-right dropdown
* Toggle sample database credentials

### Fixed
* Redshift: schema preview
* Added missing font file


## [2.0.2] - 2015-05-31

### Added
* Automatic generation of a SSL certificate to import data into Plotly Chart
  Editor.


## [1.0.4] - 2017-02-20

### Added
* Include credentials in the browser requests and accept credentials headers
  server-side.


## [1.0.3] - 2017-01-13

### Added
* Windows and Mac installers


## [1.0.2] - 2017-12-09

### Added
* A new RESTFUL API
* Support for scheduling and saving queries
* Support for S3, Elasticsearch, Apache Drill in addition to Postgres, Redshift,
  MySQL, MSSQL, Mariadb, SQLite
* Support for loading and saving credentials on disk
* A command-line version of the app
* A web-app version of the app
* Over 100 tests
