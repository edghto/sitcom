# sitcom
Tool to track some info about tv shows. 

## Motivation
At some point I watched about 10 tv shows at the sime time and 
I really lost tracked on witch episode I saw and when there is 
a new episode premier.

I wanted to write something in perl6 

## Limitations
* requires perl6 (but is this really a limitation??)
* works offline (you need to provide data to tool)
* uses imdb - when imdb loads information about episodes of any tv show it uses this request www_imdb_com/title/tt1234567/episodes/_ajax. It returns relativley small and clean piece of html which we try to parse generate local file .config

## Manual
`./sitcom  list | last NAME EP | report [NAME]  | add NAME FILE`

DESCRIPTION
  * `list`            returns list of all tracked tv show
  * `last NAME EP`    sets last watched episode to EP for tv show named NAME 
                     (but you really can track whatever you want with that)
  * `report [NAME]`   dumps info about tv show named NAME
  * `add NAME FILE`   parses data from file named FILE and save it under name NAME

## Usage
```bash
> wget http://www.imdb.com/title/tt1520211/episodes/_ajax -O wandering_undead.dat
> ./sticom add wandering_undead wandering_undead.dat
> ./ sitcom list
wandering_undead
> ./sitcom last wandering_undead 5     # last watched episode was 5
> ./sitcom report 
  wandering_undead
  01 23 Oct. 2016  
  02 30 Oct. 2016  
  03 6 Nov. 2016   
  04 13 Nov. 2016  
* 05 20 Nov. 2016  
  06 27 Nov. 2016  
  
....
```
