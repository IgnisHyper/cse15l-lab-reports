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

Source: https://www.geeksforgeeks.org/grep-command-in-unixlinux/

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

Source: https://www.geeksforgeeks.org/grep-command-in-unixlinux/

### `grep -n <text> <file>`
```
$ grep -n "music" ./written_2/travel_guides/berlitz2/Paris-WhatToDo.txt 
6:However delightful, sightseeing in Paris is only part of the pleasure of a visit. The shops, ranging from high-fashion salons and small specialty shops to flea markets, are among the best in the world. The town also provides plenty of opportunities for both fitness enthusiasts and fans of spectator sports. Dining (see page 92) is, of course, serious 
business in Paris. In terms of organized entertainment, Paris offers a wide array of theater, movies, and every kind of music.
33:The French take their jazz seriously, and Paris has many jazz clubs. Hot Brass (La Villette) and The New Morning (rue des Petites-Ecuries) attract big American and European musicians, while Le Dunois (rue Dunois) is an intimate place, cultivating more avant-garde music. The Lionel Hampton club at the Méridien Etoile (Porte Maillot) has a full program of guest performers. The old-established Caveau de la Huchette (rue de la Huchette in St-Germain-des-Prés) opens every night at 9:30pm for listening and dancing to a small combo or big band swing or bebop. Entrance prices of around 60–120F may include your first drink; extra drinks cost 30–60F.
34:In the realm of classical music, Paris has come back into its own, with many fine concerts at Salle Pleyel and Théâtre des Champs-Elysées, opera at the new Opéra-Bastille, and the ballet at the Opéra-Garnier. In all cases, some seats are reasonably priced, though they tend to go quickly. Look out for free concerts in churches.
```

This command made the `grep` command search the file "Paris-WhatToDo.txt" for the word "music" and return the lines that contained "music" along with the line number. This command is useful since it allows me to easily identify the lines in the file so that I can read lines before/after the searched text for further context.

```
$ grep -n "fun" ./written_2/travel_guides/berlitz2/Portugal-WhatToDo.txt 
9:Brass, bronze, and copper. Candlesticks, pots and pans, old-fashioned scales, bowls, and trays can be found across Portugal. Cataplanas make a delightful decorative or functional souvenir. The Moorish tradition of producing cooking utensils from beaten metal is maintained in the town of Loulé, in the Algarve.
20:Street markets (feiras or mercados) are fun for their atmosphere, and the goods for sale include all kinds of crafts, clothing, and food items. In Lisbon, behind São Vicente 
de Fora church, the Feira da Ladra (“Thieves’ Market”) is held on Tuesday and Saturday. Barcelos holds the country’s largest weekly market. The National Craft Fair in Vila do Conde, near Porto (July and August), and the Craft Fair in Lagoa, in the Algarve (August), both display crafts from all over the country.
53:Portugal dos Pequinitos, in Coimbra (see page 53), is a theme park of miniatures of Portugal’s most famous buildings. The narrow-gauge railways of the north also make a fun day-trip.
```

This command made the `grep` command search the file "Portugal-WhatToDo.txt" for the word "fun" and return the lines that contained "fun" along with the line number. This command is useful to allow me to easily find the lines that contain "fun" in the file itself and read lines before and after.

Source: https://www.geeksforgeeks.org/grep-command-in-unixlinux/ 

### `grep -rwil "love" <directory>`
```
$ grep -rwli "love" ./written_2/travel_guides/berlitz1
./written_2/travel_guides/berlitz1/HandRHawaii.txt
./written_2/travel_guides/berlitz1/HistoryEgypt.txt
./written_2/travel_guides/berlitz1/HistoryHawaii.txt
./written_2/travel_guides/berlitz1/HistoryIndia.txt
./written_2/travel_guides/berlitz1/HistoryItaly.txt
./written_2/travel_guides/berlitz1/HistoryJapan.txt
./written_2/travel_guides/berlitz1/IntroEdinburgh.txt
./written_2/travel_guides/berlitz1/IntroFrance.txt
./written_2/travel_guides/berlitz1/IntroGreek.txt
./written_2/travel_guides/berlitz1/IntroItaly.txt
./written_2/travel_guides/berlitz1/WhatToEdinburgh.txt
./written_2/travel_guides/berlitz1/WhatToEgypt.txt
# More lines not shown...
```

This `grep` command is recursively (through `-r`) searching through the "berlitz1" directory and returns the names of the files that contain the word "love". The file must contain the stand alone word "love" through the flag `-w`. The `-i` flag allows grep to accept any capitalization of the word, and the `-l` flag makes grep return only the file names. This command can be useful to search for an instance of a word in several text files while ignoring capitalization.

```
$ grep -rwil "love" ./written_2/travel_guides/berlitz2
./written_2/travel_guides/berlitz2/Algarve-WhatToDo.txt
./written_2/travel_guides/berlitz2/Amsterdam-Intro.txt
./written_2/travel_guides/berlitz2/Amsterdam-WhatToDo.txt
./written_2/travel_guides/berlitz2/Amsterdam-WhereToGo.txt
./written_2/travel_guides/berlitz2/Athens-History.txt
./written_2/travel_guides/berlitz2/Athens-Intro.txt
./written_2/travel_guides/berlitz2/Athens-WhatToDo.txt
./written_2/travel_guides/berlitz2/Bahamas-Intro.txt
./written_2/travel_guides/berlitz2/Bahamas-WhereToGo.txt
./written_2/travel_guides/berlitz2/Bali-History.txt
./written_2/travel_guides/berlitz2/Barcelona-WhatToDo.txt
./written_2/travel_guides/berlitz2/Beijing-WhatToDo.txt
# More lines not shown...
```

This `grep` command is recursively (through `-r`) searching through the "berlitz2" directory and returns the names of the files that contain the word "love'. The flags act the same way as above, with `w` searching for words and not substrings, `i` ignores capitalization, and `l` to return just the file name. Once again, searching directories recursively for a specific word with this command is quite useful.

Source: ChatGPT. I sourced this command from ChatGPT by asking it "what are the options for grep". It provided me with a list of options along with an example that I slightly altered to make the response from its response more readable in the terminal.
