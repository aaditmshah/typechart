# Pokémon Type Chart #

An interactive [pokémon type chart](https://cdn.rawgit.com/aaditmshah/typechart/master/index.html). Click on the table cells to change their values. See how balanced your custom pokémon type chart is. Share the URL of your custom pokémon type chart with others.

# Design #

The design of the pokémon type chart was copied from [pokemondb.net](http://pokemondb.net/type). Unfortunately, according to the author I'm [not allowed to copy](http://pokemondb.net/about) his design. If he'd let me use his design or if somebody would help me redesign the type chart then I'd greatly appreciate it.

# How Are The Stats Calculated? #

There are 18 pokémon types. Hence, each type has an 18 element weakness vector. The possible values of each vector element are 0, ½, 1 and 2. Hence, at worst a type will be weak to every other type including itself (i.e. it will have all 2s). Hence, the defense of each type is given by the formula `36 - sum of all elements`. The average defense value is 18, which means that on average the type neither resists nor is weak to any other type. A greater value means that the type takes less damage overall. A lesser value means that the type takes more damage overall.

Offensively, we need to calculate the effectiveness of each type against every type combination (whether there are any pokémon of that type combination is irrelevant). There are 171 type combinations (including the 18 single types). The offense of each type is calculated by summing its effectiveness against each type combination. The average value is 171, which means that on average the type hits every type combination for normal effectiveness. A greater value means that the type does more damage overall. A lesser value means that the type does less damage overall.

The overall effectiveness of each type is given by averaging the offense and defense. Finally, the stats shown are relative instead of absolute. For example, the steel type is resisted by 4 types and is super effective against only 3 types. Nevertheless, its offense is still slightly greater than average because the normal type (having two types resisting it, one type immune to it and no type weak to it) brings the average offense down. Thus, making a single change to the type chart changes the statistics of every type.

# License #

The license only extends to the JavaScript code because the design of the type chart belongs to [pokemondb.net](http://pokemondb.net/type).
