
# Musical genres in pop charts

## Introduction

"Popular music is a generic term for a wide variety of genres of music that appeal to the tastes of a large segment of the population, whereas pop music usually refers to a specific musical genre within popular music."

(Laurie, Timothy (2014). "Music Genre As Method". Cultural Studies Review. 20 (2), pp. 283-292.)

For the end of Module 1, in the Data Analytics Part-Time Bootcamp, we were ask to use web-scrapping and API Scavanger methods to gather data sets. We were then to employ the data manipulation techniques learned during class in order to provide an objective analysis.

(https://www.theguardian.com/music/2016/mar/17/pop-rock-rap-whatever-who-killed-the-music-genre) 

This project looks at information on musical tracks that populated the Pop Charts in the past years and correlates the bpm (beats per minute) value of each song with the standard for each musical genre.


## Data Used

- Deezer API: https://developers.deezer.com/api  specifically the '/chart' and '/tracks' endpoints
	Challenges:
	- "The number of requests per second is limited to 50 requests / 5 seconds": due to this factor I opted to reduce the chart track scavanging from the the offered 60 songs to 50.
	- "Encoding: All requests and responses must be in UTF-8": had to research a new method to clean the json response

- Musical U site: https://www.musical-u.com/scrapping '/learn/rhythm-tips-for-identifying-music-genres-by-ear/'
	Challenges:
	- 403 returned when requesting html content: added User-Agent header to each request.

- Tunebat: https://tunebat.com/ for pontual corrections on bpm value


## Questions to be answered

1.) What is the most successful bpm interval for musical hits?
2.) Is there a relation between bpm and chart position?
3.) Is there a dominant music genre in Popular Charts?
4.) Do popular genres vary throughout the years?
5.) Is there anß unpopular genre?
6.) What are the lowest and highest bpm in charts?
7.) What are the shortest and longest tracks in charts?
8.) Is there a relation between track duration and chart position?

##Notes

From the web scrapping processing, it was clear that genres are not mutually exclusive nor do they present the same interval size. This means that a song and its BPM value might fit within several musical genres.

On the Deezer API side, there was a limit of 50 requests per 5 seconds. Each chart endpoint presented 60 songs per year so I opted to reduce to the Top 50 to streamline the program runs.
The study focused in a 6 years interval from 2013 to 2018.

Finding the BPMs: Deezer returned NaNs for a small number of song's BPMs. These were manually updated with values from the TuneBat site.


## Conclusion

There was no clear difference between the yearly BPM values.

Its not clear that there is a relation between bpm and chart position, looking deeper into the data we can see that there is a wide range of BPMs in the songs that reach the Top 5.

There can be more that 1 Genre per song and each Genre’s bpm interval is not exclusive. With that in mind, the genre that comprises the most songs is Metal, followed by pop and chill-out.

There was an increase of Hip-hop and Chill-out beats in the later years
And we verify a drop in the Jazz and Funk beat range. 

- initially I assumed that the drop could mean
— less songs reaching the chart with that specific beat

However we must consider that this is the genre with narrowest range, so less likely for a randonmly selected song to fall in that range. Looking into this deeper I arranged (bins) the BPMs in equal intervals to check the how songs really were distributed then verifying that:

- the most popular range is 95-100 and, as curiosity, excluding the 100 BPM value would decrease significantly the peak
- the 120-125 interval, pertaining Jazz and Funk,  is actually quite popular
- the charts contain a highest number of middle range songs than the extremes

The track with the highest BPM in the 2013-2018 charts was The Greatest by Sia with  192.3  BPMs.

The track with the lowest BPM in the 2013-2018 charts was Human by Rag'n'Bone Man with  75.0  BPMs.

The longest track in the 2013-2018 charts was Changes by Faul & Wad with 345  seconds.

The shortest track in the 2013-2018 charts was Are You With Me (Radio Edit) by Lost Frequencies with  138  seconds.


## Further Questions

There seems to be a trend for charting songs to become shorter in more recent years 

However, the songs that reach the higher chart position tend to be longer.
