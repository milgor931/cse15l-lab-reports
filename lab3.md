# CSE 15L Lab 3

*Researching Commands*

Source used for all examples: [TECH REPUBLIC SOURCE](https://www.techrepublic.com/article/10-ways-to-use-grep-to-search-files-in-linux/)

# 1. grep -c
**Returns how many line matches grep found**

## ex.1 (1)
This example shows how using the -c option can show us how many lines in a single file match the given string. This is helpful when trying to find the count or sort the files based on the number of lines a file has with the string on it. 
```
#COMMAND
$ grep -c "Vallarta" ./skill-demo1-data/written_2/travel_guides/berlitz2/Vallarta-WhereToGo.txt

#RESULT
20
```

## ex.2 (2)
This example shows how to use the -c option to provide a clean display showing which files and how many lines in each of those files match the given string. This can be useful for finding the files with the string and sorting them later. 
```
#COMMAND
$ grep -c "chapter" ./skill-demo1-data/written_2/non-fiction/OUP/Abernathy/*.txt

#RESULT
./skill-demo1-data/written_2/non-fiction/OUP/Abernathy/ch1.txt:6
./skill-demo1-data/written_2/non-fiction/OUP/Abernathy/ch14.txt:4
./skill-demo1-data/written_2/non-fiction/OUP/Abernathy/ch15.txt:2
./skill-demo1-data/written_2/non-fiction/OUP/Abernathy/ch2.txt:2
./skill-demo1-data/written_2/non-fiction/OUP/Abernathy/ch3.txt:3
./skill-demo1-data/written_2/non-fiction/OUP/Abernathy/ch6.txt:3
./skill-demo1-data/written_2/non-fiction/OUP/Abernathy/ch7.txt:7
./skill-demo1-data/written_2/non-fiction/OUP/Abernathy/ch8.txt:5
./skill-demo1-data/written_2/non-fiction/OUP/Abernathy/ch9.txt:3
```

# 2. grep -L
**Prints the names of the file that do NOT include the search string**

## ex.1 (3)
This example shows how to use the -L option to find filenames that do NOT include the given string in their content using the .txt extension. This is helpful if we just want to know which files do NOT include a specific string when searching in the opposite case that grep is normally used for.
```
#COMMAND
$ grep -L "dumbo"  ./written_2/non-fiction/OUP/Berk/*.txt

#RESULT
./written_2/non-fiction/OUP/Berk/CH4.txt
./written_2/non-fiction/OUP/Berk/ch1.txt
./written_2/non-fiction/OUP/Berk/ch2.txt
./written_2/non-fiction/OUP/Berk/ch7.txt
```

## ex.2 (4)
This is another example of the -L option to find filenames that do NOT include the given string in their content using the .txt extension. In this case, the ch1.txt file in the Rybczynski folder contains the string "operative" so it is not shown but the other two files which DO NOT include that string are displayed.
```
#COMMAND
$ grep -L "operative"  ./written_2/non-fiction/OUP/Rybczynski/*.txt

#RESULT
./written_2/non-fiction/OUP/Rybczynski/ch2.txt
./written_2/non-fiction/OUP/Rybczynski/ch3.txt
```

# 3. grep -r
**Search for the files that match the given string in a DIRECTORY rather than a text file**

## ex.1 (5)
This -r option finds the files that have the given string using the directory name instead of having to use the * operator to make the search for text files easier. 
```
#COMMAND
 $ grep -r "Jacuzzis" ./skill-demo1-data/written_2/travel_guides/berlitz2

#RESULT
./skill-demo1-data/written_2/travel_guides/berlitz2/Vallarta-WhereToGo.txt:The mountain areas surrounding the Capalita River are also the site of many natural treasures, including the Capalitilla Cascades. About 30 km (18.5 miles) north of Tangolunda a grouping of waterfalls, with heights averaging 25 m (80 feet) form natural Jacuzzis and clear pools for swimming. The area is also popular for horseback riding and rappelling.
```

## ex.2 (6)
This is another example of using the -r option to find files with the directory name instead. In this example, I show how to find several files, not just one, unlike the one that I found in the first example of this option. 
```
#COMMAND
$ grep -r "blessed" ./skill-demo1-data/written_2/non-fiction

#RESULT
./skill-demo1-data/written_2/non-fiction/OUP/Fletcher/ch2.txt:As a “nation under God,” Americans have been both blessed and cursed by a sense of mission in the world. Covenanted with higher powers, the nation has a destiny—a “manifest destiny” as journalist John L. O’Sullivan dubbed our policy of westward expansion in the mid-1840s. The phrase took hold and gave American politicians a sense of national purpose as they annexed Texas in 1845, negotiated a division of the Oregon territory with England, and led the country into war with Mexico a year later.17 This was territorial aggrandizement in the name of the “nation under God.” These were the aggressive moves that established most of the boundaries of the western United States as they are today.
./skill-demo1-data/written_2/non-fiction/OUP/Kauffman/ch9.txt:In turn, this led me to wonder where such nice fitness landscapes arise in evolution, for not all fitness landscapes are so blessedly smooth. Some are random. Some are anticorrelated.
```


# 4. grep -i
**Ignores casing (lowercase or uppercase) on the string**

## ex.1 (7)
The -i option is helpful to search for a string in a file without worrying about whether the string is capitalized or not. This could be helpful in cases where you are looking for a word that might be capitalized or not. In this example, I search for capitalized "HELLO" and the results show examples with lowercase or mixed-casing. 
```
#COMMAND
$ grep -i "HELLO" ./skill-demo1-data/written_2/travel_guides/*/*.txt

#RESULT
./skill-demo1-data/written_2/travel_guides/berlitz1/WhereToFrance.txt:        Saint-Wandrille, Le Bec-Hellouin, and Caen, culminating in their
./skill-demo1-data/written_2/travel_guides/berlitz1/WhereToHongKong.txt:        the local people smile “hello” and, if you’re lucky, point you to a
./skill-demo1-data/written_2/travel_guides/berlitz1/WhereToItaly.txt:        (or Ca’ Grande), while gondoliers claim Othello’s Desdemona lived in
```

## ex.2 (8)
This example shows that the -i option could be helpful in a situation where you accidently capitalize letters in the search string. As you can see, by making sure that we use this option, we don't have to worry about capitalizing to find the correct results. 
```
#COMMAND
$ grep -i "bLissFul" ./skill-demo1-data/written_2/travel_guides/*/*.txt

#RESULT
./skill-demo1-data/written_2/travel_guides/berlitz1/WhereToItaly.txt:        spring with pink azaleas, was celebrated by John Keats as a “blissful
./skill-demo1-data/written_2/travel_guides/berlitz2/Nepal-History.txt:Buddha never claimed to be divine and in fact emphasized that all men could by their own efforts follow his path to enlightenment and the blissful state of nirvana, release from the cycle of repeated births and deaths. His “Four Noble Truths” are: all life is suffering; suffering is caused by desires; desires can be suppressed; and the way to become free of desires is to follow eight “right” principles — the Eightfold Path. These are right views, right intentions, right speech, right conduct, right livelihood, right effort, right mindfulness, and right contemplation.
```
