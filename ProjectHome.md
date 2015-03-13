<img src='http://easytvdb.googlecode.com/files/easytvdb-transparent.png' width='300' />
## Description ##
All the other libraries using TheTVDB database didn't fit my needs, so i wrote my own library.
All is based upon keeping it simple.
The library uses an implementation based on dictionaries, so it's very easy to get the informations from it.

### Informations contained in the dictionaries ###
  * TV Series informations
  * Episodes (with thumbnails)
  * Actors informations (with thumbnails)
  * Banners
  * Fanart

### Special features implemented ###
  * Caching (if you ask twice for the same series, it doesn't need to fetch the informations again... but if you need it, you can override it too!)
  * TV Series name match evaluation with percentage and main informations about the series
  * Only 5k simple code implementation
  * Documentation examples to show how does it works!

## Example ##
Class declaration:
```
easytv = EasyTVDB(api_key)
```

Search for a show:
```
showlist = easytv.findShow('lie to me')
```

| **Entity** | **Meaning** |
|:-----------|:------------|
| `showlist[0]` | first show found |
| `showlist[1]` | second show found... |
| `showlist[0][0]` | show id |
| `showlist[0][1]` | match percentage |
| `showlist[0][2]` | dictionary containing the show informations |


Informations in the showlist dictionary:
| **Key** | **Meaning** |
|:--------|:------------|
| `FirstAired` | Date of the first air |
| `IMDB_ID` | ID of the IMDB Database |
| `Overview` | Plot |
| `SeriesName` | Name of the Tv Series |
| `banner` | Banner of the series |
| `id` | ID of the series |
| `language` | Language used in the series |


Retrieve informations of the tv series:
```
series = easytv.tvshowToDict(show_id)
```


Access to the tv series informations:
```
series[showid]['SeriesName']
series[showid]['Banners']
series[showid]['Actors']
series[showid]['Episodes']['01x01']['Overview']
```


Retrieve the cached dictionary:
```
easytv.getCache()
```


See the example contained into the library to try it!