# Changelog


## v4.4.0 (2017-10-18)
* Flush the affinities file after writing the headers to it, so the headers
  get written in
* Remove the pointless `while` loop, encasing most of the code
* Rename the comment source functions (in `sources.py`), to make their names
  nicer and easier to type
* Rewrite the readme
* Add the `--timeout` (`-t`) argument, to terminate the script after a certain
  amount of time, if needed


## v4.3.0 (2017-10-01)
* License this under MIT
* Rename `comment_sources.py` to `sources.py`
* Remove PEP8 checking, making this project **non-**PEP8 compliant
* Add note about headers sometimes not getting written to file
* Make the `--submission (-s)` `comment_source` argparse description more descriptive
* Sort argparse flags into groups


## v4.2.0 (2017-09-14)
* Automatically specify a user agent when making Reddit requests, so this
  doesn't have to be specified manually by the user running the script


## v4.1.1 (2017-09-09)
* Bump the version from 4.0.0 to 4.1.1
  * This wasn't done for 4.1.0, hence this release


## v4.1.0 (2017-09-08)
* Create the `DEFAULTS` const class, and add default values to it
* Add the optional `--buffer-size` (`-z`) argument to change the buffer size
  when writing to `affinities.csv`
* Remove all the unnecessary globals and have them passed to the relevant functions
  when needed
* Move the "processed all users" message to the `else` section of the `try/except`
* Change the default buffer size from 256 to 512 bytes


## v4.0.0 (2017-09-04)
* Make the `__version__` available in `__main__`
* Add the `--quiet` flag, that'll hide all warnings and below
* Don't use all FTFs this year by default, allow the number be specified, and
  default to 5 if no preference
* Add the `SUBMISSION_ID` metavar for `--submission`
* Extract more constants and add those to `const.py`
* Change PushShift's `/reddit/get/comment_ids` endpoint to the working one
* Use specific dependency versions in `requirements.txt`
* Better file handling
  * Write to file every 8-10 rows, instead of every row, which should speed up the script,
    and make it more efficient
  * Reduce the number of read/write open/close operations done on `affinities.csv`
  * Remove `file` global, as it's no longer needed
* Add `unicodecsv` as a dependency to handle bytes <=> str conversions in csv operations
* Re-add the "total affinities calculated" message that was removed in v3.0.0
* **???**


## v3.0.0 (2017-08-03)
* Write the affinity values straight to the file, and sort it once all the values
  have been retrieved, to make the script less memory intensive
* Split `soulmate_finder.py` into separate files, under the `soulmate_finder`
  directory
* Have the version somewhere in the script
* Use Pushshift's API to get the FTF submissions, instead of manually searching for
  them ourselves
* Show why affinity can't be calculated if `MALAffinityException` is raised, and
  `verbose` is `True`
* Use the `logging` module instead of `print` statements
* Get rid of `vprint` and use `logging.debug` instead
* Show the FTF id on the "retrieving comment ids" message
* Add a debug message to show how many comments will be processed, if using `--ftf`
* Cleanup the readme
* Add `affinities.csv`, and `env/`, `venv/` to the gitignore
* Make all .py files PEP8 compliant, and set up Travis to check if this is the case


## v2.3.1 (2017-07-07)
* PRAW 5 support
  * Isn't breaking this script as far as I can see, so should probably be fine


## v2.3.0 (2017-06-22)
* `malaffinity` v2 support
* Better exception handling
* Always show the `MALRateLimitExceeded` message if it comes up
  * This was previously not shown by default unless the `--verbose` flag 
    was used


## v2.2.0 (2017-05-23)
* Add option to use all FTFs this year as the comment source


## v2.1.0 (2017-05-09)
* Only display the "Processing User" message for users not already processed
  * Displaying it for already processed users was pointless and too time taxing
* Make the unnecessary stdout calls optional and disabled by default
  * This can be activated using the `--verbose` flag


## v2.0.0 (2017-05-07)
* Rename project from `affinity-gatherer` to `r-anime-soulmate-finder`
* Rename `affinity_gatherer.py` to `soulmate_finder.py` and update all docs
* Use `--` for long positional args (that were at `-` already)
* Create short `-` positional args
* Add ability to search the comment body for a MAL URL via a `kwarg` 
  argument and positional argument
* Rename `praw.ini` to `praw.ini.example` and add `praw.ini` to `.gitignore`
* Also, create a `.gitignore`
* Display message if user already processed


## v1.1.0 (2017-04-09)
* Use [`MALAffinity`](https://github.com/erkghlerngm44/malaffinity)
  for affinity calculations


## v1.0.0 (2017-03-18)
* Init
