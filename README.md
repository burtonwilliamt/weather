# Weather
Personal weather website that pulls data from [the NOAA api](https://weather-gov.github.io/api/general-faqs).

You can view it here: https://burtonwilliamt.github.io/weather/

## Motivation
Why should looking at the weather force you to give up your data?

I wanted a weather app that respected my privacy. So I started reading the
privacy policies of the top weather apps available for free in the Android app
store. I wasn't happy with any of them. In some cases, the weather app would
hand over your precise geolocation for advertising. Gross!

What especially annoyed me was that many of these apps are
*relaying some one else's predictions*. They rely on NOAA or some other not-for
profit government agency to predict the weather, then they parrot it back to
you. If you pay taxes in the US, you're already paying for NOAA, so why should
you pay a middleman?

## Privacy
I tried to make this website using minimal services:
1) The website is a single static index.html file hosted on github pages (I think github probably tracks the number of visits to the site in some way).
1) If you lookup a city name using the search box, that query goes through the Open Street Maps geocoding service [nominatim](https://nominatim.org/release-docs/develop/api/Search/). The OSM privacy policy is not great (they have some user analytics software they use) but I think the worst of it is from their hosted website, and doesn't apply for the http endpoint we use.
1) The actual weather data is pulled directly from NOAA. This is done in two queries, one to translate Lat/Long into a NOAA weather grid, then a second to fetch the weather in that grid.

## TODO
- [ ] Add clips from relevant privacy policies in this doc.
- [ ] Store the NOAA weather grid in a cookie to avoid repeated lookups.
- [ ] Create a list of favorites that the use can select from (also stored in cookie).
- [ ] Either embed, or provide a link out to a radar map.
- [ ] Clothes recommendation at the top?


## Links
* Color palette: https://colorhunt.co/palette/f5efe7d8c4b64f709c213555