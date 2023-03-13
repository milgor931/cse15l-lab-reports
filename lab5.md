# CSE 15L Lab 5

*Researching (A Different) Command---find*

Source used for all examples: [HOW TO FORGE SOURCE](https://www.howtoforge.com/tutorial/linux-find-command/)

# 1. find -not
**Only returns files that do not match the given string**

## ex.1 (1)
This example shows how using the -not option can find all the files and directories that do NOT include the current string which in this case is "*.sample". This command can be useful in the case where you are only trying to see options that do not include the current string to potentially minimize results.
```
#COMMAND
$ find ./.git -not -name "*.sample"

#RESULT
./.git
./.git/config
./.git/description
./.git/HEAD
./.git/hooks
./.git/index
./.git/info
./.git/info/exclude
./.git/logs
./.git/logs/HEAD
./.git/logs/refs
./.git/logs/refs/heads
./.git/logs/refs/heads/main
./.git/logs/refs/remotes
./.git/logs/refs/remotes/origin
./.git/logs/refs/remotes/origin/HEAD
./.git/objects
./.git/objects/info
./.git/objects/pack
./.git/objects/pack/pack-b98cb6a4ca64cc7b2944f0fa07d3e03927d66064.idx
./.git/objects/pack/pack-b98cb6a4ca64cc7b2944f0fa07d3e03927d66064.pack
./.git/packed-refs
./.git/refs
./.git/refs/heads
./.git/refs/heads/main
./.git/refs/remotes
./.git/refs/remotes/origin
./.git/refs/remotes/origin/HEAD
./.git/refs/tags
```

## ex.2 (2)
This example shows how to use the -not option to display all the files in the written_2 directory which are not of the "txt" type by checking the extension. As a result, only the directories are shown, not the text files within them.
```
#COMMAND
$ find ./written_2 -not -name "*.txt"

#RESULT
./written_2
./written_2/non-fiction
./written_2/non-fiction/OUP
./written_2/non-fiction/OUP/Abernathy
./written_2/non-fiction/OUP/Berk
./written_2/non-fiction/OUP/Castro
./written_2/non-fiction/OUP/Fletcher
./written_2/non-fiction/OUP/Kauffman
./written_2/non-fiction/OUP/Rybczynski
./written_2/travel_guides
./written_2/travel_guides/berlitz1
./written_2/travel_guides/berlitz2
```

# 2. find -mindepth <NUM>
**Find files that are a minimum 'depth' or levels down in the filesystem.**

[NOTE: I found this command by looking through the 'man find' option]
 

## ex.1 (3)
This example shows the -mindepth option to display all the results that are a minimum depth of 6 levels down from the present working directory. In this case, the only result that had a depth of 6 was the git HEAD. Using this option can be useful when looking for the deepest file down in the filesystem.
```
#COMMAND
$ find . -mindepth 6

#RESULT
./.git/logs/refs/remotes/origin/HEAD
```

## ex.2 (4)
This is a different example shows the -mindepth option to display all the results that are a minimum depth of 4 levels down from the present working directory. In this case, there were many results in the written_2 directory that were 4 levels down. This command is also useful for skipping having to write */* when traversing or searching down in a filesystem if you already know how far down the files you are looking for are.
```
#COMMAND
$ find ./written_2 -mindepth 4

#RESULT
./written_2/non-fiction/OUP/Abernathy/ch1.txt
./written_2/non-fiction/OUP/Abernathy/ch14.txt
./written_2/non-fiction/OUP/Abernathy/ch15.txt
./written_2/non-fiction/OUP/Abernathy/ch2.txt
./written_2/non-fiction/OUP/Abernathy/ch3.txt
./written_2/non-fiction/OUP/Abernathy/ch6.txt
./written_2/non-fiction/OUP/Abernathy/ch7.txt
./written_2/non-fiction/OUP/Abernathy/ch8.txt
./written_2/non-fiction/OUP/Abernathy/ch9.txt
./written_2/non-fiction/OUP/Berk/CH4.txt
./written_2/non-fiction/OUP/Berk/ch1.txt
./written_2/non-fiction/OUP/Berk/ch2.txt
./written_2/non-fiction/OUP/Berk/ch7.txt
./written_2/non-fiction/OUP/Castro/chA.txt
./written_2/non-fiction/OUP/Castro/chB.txt
./written_2/non-fiction/OUP/Castro/chC.txt
./written_2/non-fiction/OUP/Castro/chL.txt
./written_2/non-fiction/OUP/Castro/chM.txt
./written_2/non-fiction/OUP/Castro/chN.txt
./written_2/non-fiction/OUP/Castro/chO.txt
./written_2/non-fiction/OUP/Castro/chP.txt
./written_2/non-fiction/OUP/Castro/chQ.txt
./written_2/non-fiction/OUP/Castro/chR.txt
./written_2/non-fiction/OUP/Castro/chV.txt
./written_2/non-fiction/OUP/Castro/chW.txt
./written_2/non-fiction/OUP/Castro/chY.txt
./written_2/non-fiction/OUP/Castro/chZ.txt
./written_2/non-fiction/OUP/Fletcher/ch1.txt
./written_2/non-fiction/OUP/Fletcher/ch10.txt
./written_2/non-fiction/OUP/Fletcher/ch2.txt
./written_2/non-fiction/OUP/Fletcher/ch5.txt
./written_2/non-fiction/OUP/Fletcher/ch6.txt
./written_2/non-fiction/OUP/Fletcher/ch9.txt
./written_2/non-fiction/OUP/Kauffman/ch1.txt
./written_2/non-fiction/OUP/Kauffman/ch10.txt
./written_2/non-fiction/OUP/Kauffman/ch3.txt
./written_2/non-fiction/OUP/Kauffman/ch4.txt
./written_2/non-fiction/OUP/Kauffman/ch5.txt
./written_2/non-fiction/OUP/Kauffman/ch6.txt
./written_2/non-fiction/OUP/Kauffman/ch7.txt
./written_2/non-fiction/OUP/Kauffman/ch8.txt
./written_2/non-fiction/OUP/Kauffman/ch9.txt
./written_2/non-fiction/OUP/Rybczynski/ch1.txt
./written_2/non-fiction/OUP/Rybczynski/ch2.txt
./written_2/non-fiction/OUP/Rybczynski/ch3.txt
```

# 3. find . -mmin <MIN> -name "*.txt"
**Find the file most recently edited. You can pass on an integer <MIN> which is the number of minutes since it's been edited.**

## ex.1 (5)
In this example, I had recently added some text to the Vallarta-WhereToGo.txt file to make an edit. Assuming that I forgot which exact file I had edited, the -mmin option can be very helpful because it shows me which files I had edited in the past <MIN> minutes. In this case, I had edited the file a minute ago so it was really quick to find.
```
#COMMAND
 $ find . -mmin 1 -name "*.txt"

#RESULT
./written_2/travel_guides/berlitz2/Vallarta-WhereToGo.txt
```

## ex.2 (6)
For this example, I had recently added some text to the Vallarta-WhereToGo.txt file to make an edit and also added some text to the Vallarta-WhatToDo.txt file. When I used the -mmin option to check the recently edited file, it showed me both files I had edited with the most recently edited file listed first. 
```
#COMMAND
$ find . -mmin 2 -name "*.txt"

#RESULT
./written_2/travel_guides/berlitz2/Vallarta-WhatToDo.txt
./written_2/travel_guides/berlitz2/Vallarta-WhereToGo.txt
```

# 4. find -iname [filename]
**Ignores casing (lowercase or uppercase) on the filename**

## ex.1 (7)
The -iname option is helpful to search for a string in a file without worrying about whether the string is capitalized or not. This could be helpful in cases where you are looking for a word that might be capitalized or not. In this example, I search for capitalized "HELLO.txt" and the results show examples with lowercase or mixed-casing. 
```
#COMMAND
$ find . -iname "Vallarta-wheretogo.tXt"

#RESULT
./written_2/travel_guides/berlitz2/Vallarta-WhereToGo.txt
```

## ex.2 (8)
This example shows that the -i option could be helpful in a situation where you accidently capitalize letters in the search string. As you can see, by making sure that we use this option, we don't have to worry about capitalizing to find the correct results. 
```
#COMMAND
$ find ./written_2/*/berlitz2 -iname "CUBA-WHATTODO.txt"

#RESULT
./written_2/travel_guides/berlitz2/Cuba-WhatToDo.txt
```
