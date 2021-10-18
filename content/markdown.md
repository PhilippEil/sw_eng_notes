# Markdown
"Markdown" is a mark-up language. These are used to format text in a simple, straight forward and code-esque way. This file is written in Markdown.

## Headings

To achieve headings like in e.g. "MS Word" Markdown provides hashes (symbol '#'). The amount of hashes dictates the order of the heading, so "heading 3" is smaller than "heading 1".

`# Title`

`## Title` 

`### Title` 

will produce

# Title
## Title
### Title

## Formatting Text
Of course Markup provides ways to make letters bold, italic and form block quotes.

` *text* `: *text*

` **text** `: **text**

` ***text*** `: ***text***

`>block of info`:
>block of info

`\`, `<br />`: will create a new line 

## Code Block 
Of corse has Markdown has also a fancy way to format Code:

```
`This is an in-line format`
```
will produce:
`This is an in-line format`
<br />

````
```
This is 
a multi 
line Format 
```
````
will produce:
```
This is 
a multi 
line Format 
```
<br />
There is also a support for numerous languages:

````
```c++
// globale variable
int a,b 

int main(){
    a = 10;
    b = 20;

    return a+b;
}
```
````

```c++
// global variable
int a,b 

int main(){
    a = 10;
    b = 20;

    return a+b;
}
```

## Links

A link can be added to every word of a sentence with `[word](url)` without spaces.

Check out this [link](https://github.com/PhilippEil/sw_eng_notes)!

## Numbered lists / Bullet lists

Creating lists with numbers or dots is very straight forward:

```
 1. this 
 2. is 
 3. a 
 4. list 
```

1. this
2. is
3. a
4. list

bullet list:
```
 * bullet 
 * list 
```

* bullet
* list



## Images

Want to insert a picture from an URL? Easy:

` ![image](https://justyy.com/wp-content/uploads/2016/01/markdown-syntax-language.png) `

produces:

![image](https://justyy.com/wp-content/uploads/2016/01/markdown-syntax-language.png)

Local Pictures:

`![image](doc/markdown-syntax-language.png)`

produces:

![image](doc/markdown-syntax-language.png)

## Tables
Creating a Table is easy too:
```
| a   | b   | c   |
| --- | --- | --- |
| 1   | 2   | 3   |
| 4   | 5   | 6   |
| 7   | 8   | 9   |
```

| a   | b   | c   |
| --- | --- | --- |
| 1   | 2   | 3   |
| 4   | 5   | 6   |
| 7   | 8   | 9   |

