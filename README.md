# ПроизводственныйКалендарь.json

## single json

[calendar.json](json/calendar.json)

## superjob

[2013](json/superjob2013.json) 
[2014](json/superjob2014.json) 
[2015](json/superjob2015.json) 
[2016](json/superjob2016.json) 
[2017](json/superjob2017.json) 
[2018](json/superjob2018.json) 

## consultant

[2011](json/consultant2011.json) 
[2012](json/consultant2012.json) 
[2013](json/consultant2013.json) 
[2014](json/consultant2014.json) 
[2015](json/consultant2015.json) 
[2016](json/consultant2016.json) 
[2017](json/consultant2017.json)
[2018](json/consultant2018.json)

## json structure

```json
{
    "holidays": [
        "2017-01-01",
        "2017-12-31"
    ],
    "preholidays": [
        "2017-02-22",
        "2017-03-07",
        "2017-11-03"
    ]
}
```

## Gradle task

```gradle
task downloadCalendar
downloadCalendar.doLast {
    def f = file("$projectDir/src/main/resources/calendar.json")
    new URL('https://raw.githubusercontent.com/d10xa/holidays-calendar/master/json/calendar.json')
        .withInputStream { i -> f.withOutputStream { it << i } }
}

```
