# Jupyter Notebook Data Aggregation Utility
How to update aggregated (grouped) data that was previously not aggregated to save you time with Python.

Imagine you are a genius marketer planner working on updating the volume of work you expect to have in the next fiscal year across geographies, marketing activities, and other categories. Still, you don’t want to spend all of your time working at a very granular level and rather you would like to work at an aggregated level, then have some magic done for you to have this updated volume of work distributed back to the detailed level for you. ✨

Imagine also that for a few rows (combinations of categories) there is no volume (it is zero) so consequently you need to update volume at an aggregated level.
For example, you have the following table that was provided by your Data team, with the following columns: Country, Service, Service Task, Service Task Type, Fiscal Year, Date, Total (Volume)
![image](https://github.com/renaudmontesMSFT/PythonDataAggregationUtil/assets/100614151/bbd2385e-ab6b-4227-aa6b-c216d3222f63)


The hierarchy goes from left to right, so for each month you can have many Service Task Types associated with a given Service Task, each Service Task falls under a Service and each Service under a Country.
But the thing is that you don’t want to spend time on the volume updates, so with the help of a nifty Python code, you convert it to:
 
![image](https://github.com/renaudmontesMSFT/PythonDataAggregationUtil/assets/100614151/eae2d3d1-34bc-498c-a976-6ca39042c58d)
 
Then you can update Volume totals at the Service Task (ST) level for each month instead of updating numbers at the Service Task Type level.
Once you have finished updating Volume totals at the aggregated level, run another nifty Python code to update volume at a granular level (i.e. Service Task Type) based on these two conditions:
1) If we had volume for a given service task type (STT), then calculate the percentage of this STT for the ST they belong to and refer to the new volume for the group, OR
2) If we have zeros in volume at STT level (for example, in September), then use the general updated volume at the ST level and distribute evenly (prorate) for each STT in that ST group.

And voila! You’ve updated your data at an aggregated level and let Python do the heavy lifting of distributing it back to the detailed level. 🎊🥳
