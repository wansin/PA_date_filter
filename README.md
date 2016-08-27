PA_date_filter

Python date filter script for UFED Physical Analyzer 5.1

Cellebrite Physical Analyzer (PA) date and time filter script

Wansin Ounkeo 2016-5-26

Tested: PA 5.02, PA 5.1, internal IronPython 2.6 shell, Win7x64 4GB RAM

This script filters for all data (including deleted data) that fall within a user-specified date range.

By default, the script does NOT apply your date filter to deleted items thereby giving 
you more data including ones with bad timestamps. You may optionally apply your date filter to deleted items which will give you less data. A log is saved to 'Logs' folder in Physical Analyzer install folder.

This script was made in response to SB178 (California Senate Bill 178)
"California Electronic Communication Privacy Act" to address
lack of automatic date filtering in UFED Physical Analyzer 5.02. 
California's SB178 in 2016 requires all search warrants to
specify a time period to search for electronically stored communications.
Any data not in the warrant time frame should be excluded.
Forensic examiners in California currently have to manually filter that 
data and the process is relatively slow and is error-prone. 

This script eases that.

PA by default, auto checks all items after processing which is found in
ds.TaggedFiles. This script relies on the checked files to work correctly.

TODO: the top level categories of data are updated in the GUI but the 
secondary categories are not updated. 

In the Python shell, ds.Models shows unique data only. 
The UFED PA GUI shows duplicate counts (in parenthesis).

changelog 2016-8-27   fix Unicode log filename issue in device's Display Name

changelog 2016-07-17  Handle EXIFTime stamps that have a 'T' between date and time.
                      Handle time formats in 24 hr time that use '24' instead of '0'

changelog 2016-06-26	Add DeviceInfo timestamp checks with UTC-0 default.

changelog 2016-06-23  Remove 'ActiveTime' timestamp. It is like 'Duration' - not a timestamp.

changelog 2016-06-23	ApplicationUsage has LastLaunch timestamps with mix of values showing 
                     UTC offset and no UTC offset. Treat the no UTC offset timestamps as UTC time.
