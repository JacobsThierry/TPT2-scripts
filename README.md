Hey hey,

TPT2 ai script do not have a built in array system : it's a pain. I could'n find any array implementation, so I made one myself for d0sboots's editor ( https://d0sboots.github.io/perfect-tower/ ) using lua and macros.

**How to use**
Copy the code on top of your script or make a new file in the editor and add `:import array` on top of your script.

There are 6 mains functions :
`createArray(elems)`
Create a new array. The parameter is a string of element, separated by a semicolon.
Exemple :
`createArray("a;b;c")` 
This cannot be used with strings calculated in game.

`createEmptyArray(length)`
Create an empty array. Cannot be used with a length calculated in game.

`get(list, index)`
return the element at index

`append(list, elem)`
Add an element at the end of a list.

`insert(list, elem, index)`
Add an element at index. If index is greater than the length of the list, the element will be added at the end of the list.

`pop(list, index)`
Remove the element at index.

`listLength(list)`
Return the length of the list

**Limitation**

By default, the maximum length of an element is 40 characters. This number was chosen arbitrarily and can be edited by replacing the '40' in `#paddingSize 40`
By default you can't use the character ∙. This can be changed by replacing `#paddingChar ∙` in the script.

**Examples**

Here is a random example of what you can do with arrays :
https://github.com/JacobsThierry/TPT2-scripts/blob/main/testArray

Here is a "real" script that use arrays. 
This script is spoiling something in the end game, be advised : https://github.com/JacobsThierry/TPT2-scripts/blob/main/infDisabler

**Tips**

* Do not hesitate to chain multiple function on a single line. `myArray = {pop({append({createArray("a;b;c;d")},'e')}, 5)}` is perfectly valid.
* You can use only one array instead of x variables in a script. This can save you a few lines if needed. I may soon make a dictionnary to make this process even easier.


**Disclaimer**

You should expect some bugs, I didn't tested everything rigorously.
