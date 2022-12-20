# Global UFO Sightings<br><br/>

### Dashboard
<p align="center">
<img width="650em" src="https://github.com/Power-BI-Solutions/Global-UFO-Sightings/blob/main/UFO%20Sightings.gif" align = "center"/>
</p>
<br><br/>

### Data Source
- [National UFO ReportingCenter](http://www.nuforc.org/webreports/ndxpost.html)

<br><br/>

### Custom Measures

```dax
Total Sightings = COUNTA(reports[Posted])
``` 

```dax
% in American Southwest = 
DIVIDE([American Southwest Sightings], [Total Sightings], 0)
``` 

```dax
% suspected hoax = 
DIVIDE([Suspected Hoax], [Total Sightings], 0)
``` 

```dax
American Southwest Sightings = 
CALCULATE(
    [Total Sightings],
    reports[State] = "CO" ||
    reports[State] = "NM" ||
    reports[State] = "AZ"||
    reports[State] = "CA" ||
    reports[State] = "TX" ||
    reports[State] = "UT")
``` 

```dax
Suspected Hoax = 
CALCULATE(
    [Total Sightings],
    CONTAINSSTRING(reports[Summary], "oax"))
``` 
<br><br/>

### Model

<p align="center">
<img width="650em" src="https://github.com/Power-BI-Solutions/Global-UFO-Sightings/blob/main/ufo_data.png" align = "center"/>
</p>
<br><br/>

### Acknowledgement
Project is a part of [WoW Power BI (Workout Wednesday) Challenge](https://www.workout-wednesday.com/pbi-2021-w05/)
- [Drill down](https://www.youtube.com/watch?v=QMwdKqZ6eBg&t=3s)



