---
title: Time
header:
  image: "/assets/images/unit_images/u02/header.jpg"
  caption: 'image by <a href="https://pixabay.com/de/users/arielrobin-2483349/?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=1509707">Ariel</a> on <a href="https://pixabay.com/de//?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=1509707">Pixabay</a>'
---
<!--more-->
In R, dates and times are special data types (classes), not just text strings. They contain information about order (which observation comes before another) and distance, and also the position in cycles of year, month, weeks. A characterstring may look like a date, but has a different class.

```{r}
c1 <- "2024-01-01"
c2 <- "2024-01-02"
class(c1); class(c2)
#c2-c1 results in error
```
here, we cannot calculate the difference, but it will work with date/time formats.


R mainly uses two types of time-related classes:

`Date`represents a calender date - naturally, the resolution is days.

```{r}
d1 <- as.Date("2024-01-01")
d2 <- as.Date("2024-01-02")
class(d1); class(d2)
d2-d1
```
Internally, dates are represented as the number of days since 1970-01-01, with negative values for earlier dates.




`POSIXct` represents date **and** time. Here, the resolution is seconds.

```{r}
t <- as.POSIXct("2024-01-01 12:30:00", tz = "UTC")
class(t)
```

## Date formats
A format describes how a date is written as text.

| Format  | Example |
|---------|---------|
|%Y-%m-%d|2024-01-31|
|%d.%m.%Y|31.01.2024|
|%m/%d/%Y|01/31/2024|
|%Y-%m-%d %H:%M:%S|2024-01-31 14:00:00|


## Converting

Convert to date or time using `as.Date()` or `as.POSIXct()`, respectively.
If your character is not in the standard form, specify the format:

```{r}
as.Date("31.01.2024", format = "%d.%m.%Y")
```

Attention: `as.POSIXct` assumes the timestamp is given in UTC. You can overwrite that by adding the argument `tz`

```{r}
t <- as.POSIXct("2024-01-01 12:00:00", tz = "UTC")
t
t_berlin <- as.POSIXct("2024-01-01 12:00:00", tz = "Europe/Berlin")
t_berlin
```

To convert between timezonesand given a defined timezone, you can again use `as.POSIXct`:

```{r}
t_berlin_utc <- as.POSIXct(t_berlin, tz="UTC")
t_berlin_utc
```


## Extracting components

You can extract calender components using `as.POSTIXlt()`

```{r}
tt <- as.POSIXlt()
```
This creates a list-like object with named components.

|Component	|Code	|Meaning|
|-----------|-------|-------|
|Hour	|tt$hour	|0–23|
|Day of week	|tt$wday	|0–6 (Sunday = 0)|
|Month	|tt$mon	|0–11|
|Day of month	|tt$mday	|1–31|
|Year	|tt$year	|years since 1900|