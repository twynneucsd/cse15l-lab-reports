# Lab Report 3 - Researching Commands
***
**Part 1 - Setting up the foundation for researching the `grep` command**

During the lab over week 4, the command I felt like I was the most comfortable with was `grep` so I decided that I would research this command.

In order to setup my usage of `grep`, I downloaded the [docsearch](https://github.com/ucsd-cse15l-s23/docsearch) repository from github to make use of the "technical" directory.

With this set up, I am ready to make use of `grep`. 

***
**Part 2 - learning different usages of the `grep` command**

**Important** - For all of the following usages of `grep`, I learned how to use them from this [article](https://www.hostinger.com/tutorials/grep-command-in-linux-useful-examples/#:~:text=Grep%2C%20or%20global%20regular%20expression,any%20lines%20that%20contain%20it.).

**Command Option 1: `query`**

The `query` option for `grep` locates keywords and is the basic option I will utitlize for following command options. Specifically, I want to use the option where you can type two queries to locate files that contain two keywords of choice.

The first search that I did was `$ grep 'high speed\|chase'  technical/911report/*` , where in this instance I am searching for both queries "high speed" and "chase" within the 911report directory. In order to search for two queries generally, you would replace the ones that I wrote in with whatever you wanted.

This search returned: 

`technical/911report/chapter-1.txt:    On the morning of 9/11, there were only 37 passengers on United 93-33 in addition to the 4 hijackers. This was below the norm for Tuesday mornings during the summer of 2001. But there is no evidence that the hijackers manipulated passenger levels or purchased additional seats to facilitate their operation.`

`technical/911report/chapter-1.txt:    The NEADS technician who took this call from the FAA immediately passed the word to the mission crew commander, who reported to the NEADS battle commander: Mission Crew Commander, NEADS: Okay, uh, American Airlines is still airborne. Eleven, the first guy, he's heading towards Washington. Okay? I think we need to scramble Langley right now. And I'm gonna take the fighters from Otis, try to chase this guy down if I can find him.`

`technical/911report/chapter-13.2.txt:                not reveal the purchase of any tickets beyond those the hijackers used for`

`technical/911report/chapter-13.2.txt:                the hijackers purchased firearms, use of a gun would be inconsistent with the`

`technical/911report/chapter-13.2.txt:                Langley Air Force Base to chase the aircraft, but they would need "executive"orders`

`technical/911report/chapter-13.4.txt:                institutional investor with no conceivable ties to al Qaeda purchased 95 percent of`

`technical/911report/chapter-13.4.txt:            29. On the purchase of the car, see FBI report, "Hijackers Timeline," Nov. 14, 2003`

`technical/911report/chapter-13.4.txt:                purchased flight equipment from an instructor at the Sorbi Flying Club in San Diego.`

`technical/911report/chapter-13.4.txt:                report, interrogation of detainee, Jan. 22, 2002. For the ammonium nitrate purchase,`

`technical/911report/chapter-13.4.txt:            81. For Shehhi's ticket purchase, see FBI report, "Hijackers Timeline," Dec. 5, 2003`

`technical/911report/chapter-13.5.txt:                debit cards to pay for hotel rooms; and Hazmi used his card on August 27 to purchase`

`technical/911report/chapter-2.txt:                long, and one thought he could pronounce it genuine. Al Qaeda apparently purchased`

`technical/911report/chapter-2.txt:                immigration procedures, purchase and import vehicles and weapons, and enjoy the use`

`technical/911report/chapter-2.txt:                Members of the cells rented residences, and purchased bomb-making materials and`

`technical/911report/chapter-2.txt:                up some of the operatives. The suicide trucks were purchased shortly before the`

`technical/911report/chapter-5.txt:                lodging for them and helped them purchase airline tickets for their onward travel.`

`technical/911report/chapter-5.txt:                purchased flight simulator software and a few movies depicting hijackings. To house`

`technical/911report/chapter-6.txt:                operatives, and provided the money needed to purchase explosives and equipment.`

`technical/911report/chapter-7.txt:                lived. For example, when they purchased a used car (with cash), they bought it from`

`technical/911report/chapter-7.txt:                Salmi, stands out. In July 2000, Salmi purchased $4,000 in traveler's checks at a`

`technical/911report/chapter-7.txt:                of cash and traveler's checks purchased in the UAE and Saudi Arabia. Seven muscle`

`technical/911report/chapter-7.txt:                hijackers are known to have purchased a total of nearly $50,000 in traveler's checks`

`technical/911report/chapter-7.txt:                16, Binalshibh returned to Hamburg, using a ticket Atta had purchased for him`

`technical/911report/chapter-7.txt:                Aysel Senguen, Jarrah's girlfriend, purchased a one-way ticket for Jarrah from Miami`

`technical/911report/chapter-7.txt:            August 13 through August 20. Moussaoui also purchased two knives and inquired of two`

`technical/911report/chapter-7.txt:                best way for the operatives to purchase plane tickets and the assignment of muscle`

`technical/911report/chapter-7.txt:                Hazmi, and Hanjour all purchased tickets for another set of surveillance flights.`

`technical/911report/chapter-7.txt:                make purchases suggesting that the planning was coming to an end. In mid-August, for`

`technical/911report/chapter-7.txt:                On August 22, moreover, Jarrah attempted to purchase four GPS units from a pilot`

`technical/911report/chapter-7.txt:                when he also purchased three aeronautical charts.`

`technical/911report/chapter-7.txt:            Perhaps most significant, however, was the purchase of plane tickets for September`

`technical/911report/chapter-7.txt:                flights. All 19 tickets were booked and purchased between August 25 and September`

`technical/911report/chapter-7.txt:                purchased his tickets on August 20 and departed Hamburg for Karachi on September`

`technical/911report/chapter-8.txt:                martial arts training, and intended to purchase a global positioning receiver. The`



Wow! Definitely A lot to unpack here. Firstly, the directory I chose is the "911report" subdirectory under "technical", and the "*" tells `grep` to look at all files in that directory for the search. Now, for the search itself, if you are caught up to date with youtube or twitch or other social media platforms, my search would make a lot more sense. Recently, livestreamed police chases have been gaining a lot of viewers and publicity hence why I searched for "high speed" and "chase". From a quick glance, it appears that we did not find many "high speed" results and found a lot of results for words like "purchase" that contain the keyword "chase". Since I was looking for differing results than the ones that appeared, I will try other similar keywords like "cruiser" or "speed limit" and see if we can find anything:

To search for these similar keywords, I then used `$ grep 'cruiser\|speed limit'  technical/911report/*`.

However, this command ended up turning an empty result, meaning neither of the key words were located.

**Command Option 2: `-w`**

As observed in the above examples, the information I was searching for when typing the keyword "chase" resulted in showing me a bunch of places where "purchase" was found. However, these two words have very differing meanings. Therefore, I can use the `-w` option for `grep` to single out the exact word "chase" rather than all words that contain the same phrase.

To do this, I use the following command: `$ grep -w chase  technical/911report/*`

To my surprise there are actually results!

The command line returns:

`technical/911report/chapter-1.txt:    The NEADS technician who took this call from the FAA immediately passed the word to the mission crew commander, who reported to the NEADS battle commander: Mission Crew Commander, NEADS: Okay, uh, American Airlines is still airborne. Eleven, the first guy, he's heading towards Washington. Okay? I think we need to scramble Langley right now. And I'm gonna take the fighters from Otis, try to chase this guy down if I can find him.`

`technical/911report/chapter-13.2.txt:                Langley Air Force Base to chase the aircraft, but they would need "executive"orders`

While the amount of search results here visibly pales in comparison to the previous time I searched for "chase", this time by using `grep -w` I found results that more closely matched what I was actually looking for.


For my next example of the `-w` option, I opted to search in the directory "technical/biomed/*" in order to change up the pool of results I may see. I will also demonstrate the effects of `-w` in a different way from the previous example.

First, I ran the commands `$ grep -w lab technical/biomed/* > labcounter.txt` and `$ grep -w laboratory technical/biomed/* > laboratorycounter.txt`. Simply put, these search for the exact words "lab" and "laboratory" within the chosen directory and create new text files that I can examine to see the frequency of these words.

I then used the `wc` command to make this examination: 

First, on "labcounter.txt", the file that tracks the amount of times the word "lab" was used: 

`$ wc labcounter.txt`
  
  `42  429 4185 labcounter.txt`
  
  We can see it located 42 lines as indicated by the first number where "lab" was found.
  
  For "laboratory", we get differing results:
  
  `$ wc laboratorycounter.txt`
  
  `363  3200 35533 laboratorycounter.txt`
  
  In fact, we observe that "laboratory" was found in many more instances than "lab" (363 lines!). If we used `grep lab` rather than `grep -w lab` , we can guarentee the frequency of "lab" as a keyword would be significantly higher than "laboratory" which contains the word, however we see that the opposite is true for this case!
  
  **Command Option 3: `-A`**
  
  The `-A` option for `grep` searches for a query and returns the line where it is located, but also seems to return the lines that follow it as well for a specified length.
  
  At first, I selected a random file from the "biomed" subdirectory to run my tests on. I settled on "independent technical/biomed/1471-2105-3-30.txt". I will use this same file for Command Option 4's test results.
  
  I then used the command `$ grep -A1 independent technical/biomed/1471-2105-3-30.txt` which returned:

`eliminated, until ~5 quasi independent motifs are`
          
         ` obtained whose scores can be added (details in additional`

`--`
         
         `independent runs (with typically 2-4 runs done for each`
          
          `data set).`
  

While its not yet fully clear what is going on, we can see that after the lines with "independent" searched as a keyword the following lines are printed. In both of the found results, we can see that the next line actually had really important context for what was happening in the previous lines that we were searching for.

Testing this command again I ran : `$ grep -A2 independent technical/biomed/1471-2105-3-30.txt` , with the difference being I used `-A2` rather than `A1`

This returned:
 
` eliminated, until ~5 quasi independent motifs are`
         
        ` obtained whose scores can be added (details in additional`
         
        ` File 7).`

`--`
          
          `independent runs (with typically 2-4 runs done for each`
         
        ` data set).`
        
        
We can see here that `-A` now displayed 2 lines following our searched keyword, which ended up completing the sentence for the first result. Clearly, the way the `-A` option functions is that the number behind it indicates how many lines following the searched keyword should also be returned.


**Command Option 4: `-B`***

The `-B` option for `grep` is very similar to `-A` but returns the lines before the searched keyword instead. This is very useful for gathering a pretext to the things you may be locating with `grep`.

Here is its usage:

First command: `$ grep -B1 independent technical/biomed/1471-2105-3-30.txt`

This returned:

 `next remaining motif is retained and overlaps with it are`
 
         ` eliminated, until ~5 quasi independent motifs are`
          
`--`

         ` 4) the preceding conditions were met in two`
          
          `independent runs (with typically 2-4 runs done for each`
          
We can see here that now we have pretext rather than finding things after the line containing our keyword "independent".


Using a similar command: `$ grep -B2 independent technical/biomed/1471-2105-3-30.txt`

We get:

  `it under shifts and a limited number of mutations. The`
         ` next remaining motif is retained and overlaps with it are`
         ` eliminated, until ~5 quasi independent motifs are`
`--`
         ` bases.`
         ` 4) the preceding conditions were met in two`
          `independent runs (with typically 2-4 runs done for each`
          
          
We can observe that similarly to `-A` the number next to `-B` indicates how many lines previous to the one with your keyword you want to be returned. This can be used if you use `grep` to find something and you are very confused of the context, and `-B` can be used to search any given amount of liens of context that you may need.

There is also a way to combine the functionality of `-A` and `-B` with the `-C` option that returns lines both before and after the one where your chosen query was located.












