# Week 4/5 Lab Report - Abel Preciado
## `grep` command options
### `grep -rl <text>`
```
$ grep -rl "Poland"
.git/index
most-characters.txt
written_2/travel_guides/berlitz1/IntroJerusalem.txt
written_2/travel_guides/berlitz1/WhereToFrance.txt
written_2/travel_guides/berlitz2/Berlin-History.txt
written_2/travel_guides/berlitz2/Poland-History.txt
written_2/travel_guides/berlitz2/Poland-WhatToDo.txt
```

This command made the `grep` command search recursively within various directories and text files for the text "Poland" and returned the name of the files that contained "Poland". We avoid having to use `find` to get a list of all text files while also only printing the file names so we can avoid having to see the specific lines in each file that contain "Poland".

```
$ grep -rl "Brazil"
written_2/non-fiction/OUP/Berk/ch1.txt
written_2/travel_guides/berlitz1/HistoryMadeira.txt
written_2/travel_guides/berlitz1/IntroMadeira.txt   
written_2/travel_guides/berlitz1/WhatToMadeira.txt  
written_2/travel_guides/berlitz1/WhereToHongKong.txt
written_2/travel_guides/berlitz1/WhereToMadeira.txt 
written_2/travel_guides/berlitz1/WhereToMalaysia.txt
written_2/travel_guides/berlitz2/Algarve-History.txt   
written_2/travel_guides/berlitz2/Algarve-Intro.txt     
written_2/travel_guides/berlitz2/Algarve-WhereToGo.txt 
written_2/travel_guides/berlitz2/Barcelona-WhatToDo.txt
written_2/travel_guides/berlitz2/Berlin-WhereToGo.txt
written_2/travel_guides/berlitz2/Canada-WhereToGo.txt     
written_2/travel_guides/berlitz2/CanaryIslands-History.txt
written_2/travel_guides/berlitz2/Portugal-History.txt  
written_2/travel_guides/berlitz2/Portugal-WhereToGo.txt
```

This command made the `grep` command search recursively within various directories and text files for the text "Brazil" and returned the name of the files that contained "Brazil". Once again, we avoid having to use `find` to get a list of all text files while keeping the terminal relatively clean since only file names are printed to the console.

### `grep -c <text> <file>`

```
$ grep -c "Cuba" ./written_2/travel_guides/berlitz2/Cuba-History.txt 
25
```

This command made the `grep` command search the file "Cuba-History.txt" and return the count of the number of lines that contained the word "Cuba". This allows us to utilize the `grep` command to directly count the number of lines that contained "Cuba" without having to save the results into a text file and using `wc`.

```
$ grep -c "gold" ./written_2/travel_guides/berlitz2/California-History.txt 
7
```

This command made the `grep` command search the file "California-History.txt" and return the count of the number of lines that contained the word "gold". This allows us to potentially see how often "gold" is discussed in the history of California by comparing this number to the total number of lines in the file.

###

```

```

Placeholder

```

```

Placeholder

###

```

```

Placeholder

```

```

Placeholder

###

```

```

Placeholder

```

```

Placeholder
