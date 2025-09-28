# Principes

L'idée serait d'avoir une génération de donjons afin d'obtenir un résultat similaire à ce que l'on pouvait obtenir sur Dark Chronicle, donc des "niveaux" qui donne l'impression que les salles et couloirs sont placé de manière aléatoire, mais logique quand même.

POour ce qui est de l'organisation, on aurait plusieurs tables / db qui nous permettrait d'obtenir les données qui nous seront nécéssaire: <br>
- Une table contenant la liste des étages. Cette table nous permettrait d'avoir les donnée voulu pour chaques étages. <br>
   > (exemple : { <br>
        "biome" : "Forest", //Pour identifier dans qu'elle région du jeu on ce situe <br>
        "floor" : 6, //Pour identifier l'étage <br>
        "size" : [12, 12], //Pour la taille maximale de l'étage <br>
        "room" : 4, //Pour la quantité de salles que l'étage contient <br>
        "exit" : 2, //Pour la quantité de sortie vers l'étage suivant, si on veux avoir des cas de donjons à embranchement <br>
        "intersection" : 6, //Pour la quantité d'intersection que l'étage contient <br>
        "hallway" : 20, //Pour la longueur minimale de couloirs de l'étage (parce que on veux pas formcément que les étages puisse être miniature) <br>
        "monster_list" : ["monster_A", "monster_A", "monster_B", "monster_C", "monster_D", "monster_D", "monster_E",... ], //Pour la liste des monstres qui peuple l'étage, qui tapera dans la table des monstres pour en obtenir les infos <br>
        "chest_quantity" : 9, //Pour la quantité de coffres présent dans l'étage <br>
        "junk_max_quantity" : 14, //Pour la quantité max de "junk" jetable (caisses, tonneaux, rocher, ect.) présent dans l'étage <br>
        "bgm" : "forest_bgm_3" //Pour le BGM utilisé pour cet étage <br>
   > }) <br>
- Une table contenant la liste des monstres. Cette table nous permettrait d'avoir les données de chaque monstres. <br>
   > (exemple : { <br>
        
   > }) <br>
- Une tabke contenant la liste des objets. Cette table nous permettrait d'avoir les données de chaque objets. <br>
   > (exemple : { <br>
        
   > })

La création d'un étage se ferait en plusieurs étapes: <br>
- Premièrement, le positionnement de l'entrée, de la sortie, des salles, embranchements, couloirs et cul de sac. <br>
- Ensuite, on place les coffres, monstres et "junk" dans le niveau en prenant en compte la capacité max de chaque chunk et la capacité max de l'étage.<br>