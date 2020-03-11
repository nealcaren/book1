---
redirect_from:
  - "/2-python"
interact_link: content/2_Python.ipynb
kernel_name: python3
title: 'Python Basics'
prev_page:
  url: /1_Setup
  title: 'Getting Started'
next_page:
  url: 
  title: ''
comment: "***PROGRAMMATICALLY GENERATED, DO NOT EDIT. SEE ORIGINAL FILES IN /content***"
---
# Python Basics

 


This section introduces some of the most relevant aspects of working with Python for social scientists. This includes the different data types available and ways to modify them. 


## Strings


According to Wikipedia, 

> Caribbean reef squid have been shown to communicate using a variety of color, shape, and texture changes.


To store that in Python, create a new variable called `sentence`



{:.input_area}
```python
sentence =  'Caribbean reef squid have been shown to communicate using a variety of color, shape, and texture changes.'
```


The text is surrounded by a single quote (`'`) on each side. 
To make sure that you typed the tweet correctly, you can type `sentence`:



{:.input_area}
```python
sentence
```





{:.output .output_data_text}
```
'Caribbean reef squid have been shown to communicate using a variety of color, shape, and texture changes.'
```



You can get almost the same response using the `print` function:





{:.input_area}
```python
print(sentence)
```


{:.output .output_stream}
```
Caribbean reef squid have been shown to communicate using a variety of color, shape, and texture changes.

```

The only difference is that the first response was wrapped in single quotes and the second wasn’t. As a side note, the single quotes weren’t because you put them there. If you used double quotes, Python would still show a single-quote.



{:.input_area}
```python
sentence =  "Caribbean reef squid have been shown to communicate using a variety of color, shape, and texture changes."

sentence
```





{:.output .output_data_text}
```
'Caribbean reef squid have been shown to communicate using a variety of color, shape, and texture changes.'
```



In addition to `'` and `"`, strings can also be marked with a `'''`. This last one is particularly useful when your text contains contractions or quotation marks. 



{:.input_area}
```python
new_sentence = '''According to Wikipedia, "Caribbean reef squid have been shown to communicate using a variety of color, shape, and texture changes."'''
```




{:.input_area}
```python
print(new_sentence)
```


{:.output .output_stream}
```
According to Wikipedia, "Caribbean reef squid have been shown to communicate using a variety of color, shape, and texture changes."

```

#### Exercise


Create a new string called <code>food</code>  that is a sentence about your most recent meal. Display the contents of your new string. 




{:.input_area}
```python
# Type your answer here
```




{:.input_area}
```python
food = 'I had a pizza for lunch.'
print(food)
```


{:.output .output_stream}
```
I had a pizza for lunch.

```

### String Manipulation

Python has a few tools for manipulating text, such as `lower` for making the string lower-case.



{:.input_area}
```python
sentence.lower()
```





{:.output .output_data_text}
```
'caribbean reef squid have been shown to communicate using a variety of color, shape, and texture changes.'
```



This did not alter the original string, however.



{:.input_area}
```python
sentence
```





{:.output .output_data_text}
```
'Caribbean reef squid have been shown to communicate using a variety of color, shape, and texture changes.'
```



In Python, strings are immmutable, meaning once created, they can not be altered in place. We could store the results in a new variable.



{:.input_area}
```python
lower_sentence = sentence.lower()

lower_sentence
```





{:.output .output_data_text}
```
'caribbean reef squid have been shown to communicate using a variety of color, shape, and texture changes.'
```



#### Exercise

Create a new, lower cased version of your <code>food</code> string.




{:.input_area}
```python
# Your answer here.

```




{:.input_area}
```python
food_lower = food.lower()
```


We can also `replace` text within the string.



{:.input_area}
```python
sentence.replace("Caribbean reef squid", "Velociraptors")
```





{:.output .output_data_text}
```
'Velociraptors have been shown to communicate using a variety of color, shape, and texture changes.'
```



`replace` can also be used to remove text without replacement.



{:.input_area}
```python
sentence.replace(".", "")
```





{:.output .output_data_text}
```
'Caribbean reef squid have been shown to communicate using a variety of color, shape, and texture changes'
```



As before, this does not alter the original string. If you wanted to save the string edits, you would need to create a new variable.








{:.input_area}
```python
edited_sentence = sentence.lower()
print(edited_sentence)
```


{:.output .output_stream}
```
caribbean reef squid have been shown to communicate using a variety of color, shape, and texture changes.

```

If you were doing a series of manipulations, you could reuse a varaiable name, although it is best practices to keep a version of the original string in case you ever need to go back to it. 



{:.input_area}
```python
edited_sentence = sentence.lower()
print(edited_sentence)

edited_sentence = edited_sentence.replace(".", "")
print(edited_sentence)
```


{:.output .output_stream}
```
caribbean reef squid have been shown to communicate using a variety of color, shape, and texture changes.
caribbean reef squid have been shown to communicate using a variety of color, shape, and texture changes

```

You can also stack multiple transformations together, although combining too many may make your code harder to follow.



{:.input_area}
```python
edited_sentence.replace(".", "").lower()
```





{:.output .output_data_text}
```
'caribbean reef squid have been shown to communicate using a variety of color, shape, and texture changes'
```



#### Exercise

Create a new string called <code>boring</code> that removes the exclamation marks and capitalization from the sentence "Way to go!!!".  




{:.input_area}
```python
boring = "Way to go!!!".replace('!','').lower()
print(boring)

# Alternatively:
exciting = "Way to go!!!".replace('!','')
boring   = exciting.replace('!','')
boring   = boring.lower()
print(boring)
```


{:.output .output_stream}
```
way to go
way to go

```

## Slicing

If you had a very long text, such as the entire text of a Wikipedia article, you might only want to look at the first few characters. In Python, this is called by slicing.



{:.input_area}
```python
sentence
```





{:.output .output_data_text}
```
'Caribbean reef squid have been shown to communicate using a variety of color, shape, and texture changes.'
```





{:.input_area}
```python
sentence[0:20]
```





{:.output .output_data_text}
```
'Caribbean reef squid'
```



A slice is signaled with brackets (`[]`). The first number is the starting position, where 0 indicates the beginning. This is followed by a colon (`:`) and then the end position, which, in this case, is a 20. Note that this is splitting on characters, not words.

Here is a section from the middle of the string:



{:.input_area}
```python
sentence[20:32]
```





{:.output .output_data_text}
```
' have been s'
```



For convience, if you ommit the number before the colon, it defaults to the string beginning.



{:.input_area}
```python
sentence[:40]
```





{:.output .output_data_text}
```
'Caribbean reef squid have been shown to '
```



Ommitting the second number defaults to the end.



{:.input_area}
```python
sentence[40:]
```





{:.output .output_data_text}
```
'communicate using a variety of color, shape, and texture changes.'
```



Finally, negative numbers are interpreted as distance from the end of the string.



{:.input_area}
```python
sentence[-20:]
```





{:.output .output_data_text}
```
'and texture changes.'
```



#### Exercise

Create a new string called `s` that contains `The weather is hot and humid today.` Find the slices for each of the following :
* `The we`
* `today.`
* `hot and humid`





{:.input_area}
```python
#Your answer here.
```




{:.input_area}
```python
s = 'The weather is hot and humid today.'
print(s[:6])
print(s[-6:])
print(s[15:-7])
```


{:.output .output_stream}
```
The we
today.
hot and humid

```

# Numbers

We can also count the number of characters in a string with the `len` function.



{:.input_area}
```python
len(sentence)
```





{:.output .output_data_text}
```
105
```



In this case, Python returned an interger instead of string. This also can be stored in a variable.



{:.input_area}
```python
sentence_length = len(sentence)
```




{:.input_area}
```python
sentence_length
```





{:.output .output_data_text}
```
105
```



#### Exercise.

What is the length of `How many dogs do you own?`? Store it in a variable called `sl`.




{:.input_area}
```python
# Your answer here.
```




{:.input_area}
```python
sl = len('How many dogs do you own?')
print(sl)
```


{:.output .output_stream}
```
25

```

Since this is a number, we can do standard math operations with it.



{:.input_area}
```python
print(sentence_length * 3)
```


{:.output .output_stream}
```
315

```



{:.input_area}
```python
print(sentence_length / 2)
```


{:.output .output_stream}
```
52.5

```



{:.input_area}
```python
print(sentence_length + sentence_length)
```


{:.output .output_stream}
```
210

```

#### Exercise

What is one-third the length of `sl`?




{:.input_area}
```python
# Your answer here
```




{:.input_area}
```python
print(sl/3)
```


{:.output .output_stream}
```
8.333333333333334

```

As with strings, these can be saved in new variables.



{:.input_area}
```python
double_length = sentence_length + sentence_length

print(double_length)
```


{:.output .output_stream}
```
210

```

These same operators also work with strings.



{:.input_area}
```python
print(sentence * 2)
```


{:.output .output_stream}
```
Caribbean reef squid have been shown to communicate using a variety of color, shape, and texture changes.Caribbean reef squid have been shown to communicate using a variety of color, shape, and texture changes.

```



{:.input_area}
```python
print(sentence + sentence)
```


{:.output .output_stream}
```
Caribbean reef squid have been shown to communicate using a variety of color, shape, and texture changes.Caribbean reef squid have been shown to communicate using a variety of color, shape, and texture changes.

```

The operators can't be used to combine different data types, however.



{:.input_area}
```python
print("The sentence was " + sentence_length + "characters.")
```


{:.output .output_traceback_line}
```

    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-39-9041347a8e39> in <module>
    ----> 1 print("The sentence was " + sentence_length + "characters.")
    

    TypeError: can only concatenate str (not "int") to str


```

Conviently, Python the `str` function will convert an interger to a string.



{:.input_area}
```python
print("The sentence was " + str(sentence_length) + " characters.")
```


{:.output .output_stream}
```
The sentence was 105 characters.

```

I manually had to include the spaces before and after `sentence_length`. Otherwise, it all is smushed together. 



{:.input_area}
```python
print("The sentence was" + str(sentence_length) + "characters.")
```


{:.output .output_stream}
```
The sentence was105characters.

```

#### Exercise

Print `The length of the word "hippopotamus" is [x].` where `[x]` is the length of the word hippopotamus .




{:.input_area}
```python
#Your answer here.
```




{:.input_area}
```python
l = len('hippopotamus')
s = 'The length of the word "hippopotamus" is ' + str(l) + '.'
print(s)
```


{:.output .output_stream}
```
The length of the word "hippopotamus" is 12.

```

## Lists

We can also `split` the sentence into a series of strings. By default, this splits based on spaces and other whitespace characters such as a line break (`\n`) or tab character (`\t`). 



{:.input_area}
```python
print(sentence.split())
```


{:.output .output_stream}
```
['Caribbean', 'reef', 'squid', 'have', 'been', 'shown', 'to', 'communicate', 'using', 'a', 'variety', 'of', 'color,', 'shape,', 'and', 'texture', 'changes.']

```

What is returned here is a third data type (the first two were strings and intergers) called a list. A list is enclosed in brackets (`[]`) and the items are seperated by commas. In this case each item is in quotation marks because they are all strings. Items in a list, however, can be of any sort.



{:.input_area}
```python
my_list = ['Speeches', 7, 'Data']
my_list
```





{:.output .output_data_text}
```
['Speeches', 7, 'Data']
```



While `len` returned the number of characters in a string, it returns the number the items in a list.



{:.input_area}
```python
len(my_list)
```





{:.output .output_data_text}
```
3
```





{:.input_area}
```python
sentence_length = len(sentence.split())
sentence_length
```





{:.output .output_data_text}
```
17
```



In the second example, the list created by `sentence.split()` is not saved in any way; only its length.

#### Exercise

Create a list called `food` that includes at least three things you ate today. Use `len` to count the number of items in the list.



{:.input_area}
```python
# Your answer here
```




{:.input_area}
```python
food = ['pizza slice', 'naan', 'cupcake', 'grape']
print(len(food))
```


{:.output .output_stream}
```
4

```

Like, strings, lists can also be sliced. The first three items of a list:



{:.input_area}
```python
words = sentence.split()
print(words[:3])
```


{:.output .output_stream}
```
['Caribbean', 'reef', 'squid']

```

We can also extract specific items from a list by their position. As it did with strings, slicing in Python starts with 0.



{:.input_area}
```python
words[0]
```





{:.output .output_data_text}
```
'Caribbean'
```



The third word:



{:.input_area}
```python
words[3]
```





{:.output .output_data_text}
```
'have'
```



The fifth word from the end:



{:.input_area}
```python
words[-5]
```





{:.output .output_data_text}
```
'color,'
```



The last two words, returned as a list:



{:.input_area}
```python
words[-2:]
```





{:.output .output_data_text}
```
['texture', 'changes.']
```



#### Exercise

Display the first two items of your `food` list. What is the last item?




{:.input_area}
```python
# Your answer here
```




{:.input_area}
```python
#Sample Answer 

print(food[:2])
print(food[-1])
```


{:.output .output_stream}
```
['pizza slice', 'naan']
grape

```

Unlike a string, lists are mutable. That means that we can remove or as is more frequently the case text analysis, add things to it. This is done with `append`.



{:.input_area}
```python
male_words = ['his', 'him', 'father']
male_words.append('brother')
print(male_words)
```


{:.output .output_stream}
```
['his', 'him', 'father', 'brother']

```

Since `append` is changing `male_words`, we do not want to use an `=`. The Python interpreter is editing our original list but not returning anything.



{:.input_area}
```python
not_going_to_work = male_words.append('brother')
print(not_going_to_work)
```


{:.output .output_stream}
```
None

```

Lists can be also be combined using `+`.



{:.input_area}
```python
gendered_words = male_words + ['her', 'she', 'mother']
print(gendered_words)
```


{:.output .output_stream}
```
['his', 'him', 'father', 'brother', 'brother', 'her', 'she', 'mother']

```

As note above, the items in a list can include a variety of data types. This includes lists.



{:.input_area}
```python
gendered_lists = [ male_words ,  ['her', 'she', 'mother'] ]
```


Note the two closing brackets next to each other. The first closes the list that ends with 'mother' while the second closes our `gendered_lists`.



{:.input_area}
```python
len(gendered_lists)
```





{:.output .output_data_text}
```
2
```



`gendered_lists` has a length of two because it contains just two items, each a list of varying lengths.



{:.input_area}
```python
print(gendered_lists)
```


{:.output .output_stream}
```
[['his', 'him', 'father', 'brother', 'brother'], ['her', 'she', 'mother']]

```

#### Exercise

Add three more items to your `food` list. Use`append` for the first item. 
For the other two, place them in a new list and then combine the two lists.




{:.input_area}
```python
# Your answer here
```




{:.input_area}
```python
# Sample answer

food.append('panini')
print(food)
food = food + ['burrito', 'box of donuts']
print(food)
print(len(food))
```


{:.output .output_stream}
```
['pizza slice', 'naan', 'cupcake', 'grape', 'panini', 'burrito', 'box of donuts', 'panini', 'burrito', 'box of donuts', 'panini']
['pizza slice', 'naan', 'cupcake', 'grape', 'panini', 'burrito', 'box of donuts', 'panini', 'burrito', 'box of donuts', 'panini', 'burrito', 'box of donuts']
13

```

# Dictionaries

A fourth useful data type is a dictionary. A dictionary is like a list in that it holds multiples items. The items in a list can be identified by their position in the list. In contrast, the values in a dictionary are associated with a keyword. The analogy here is a to a physical dictionary, which has a list of unique words, and each word has a definition. In this case, the entries are called keys, and the definitions, which can be any data type, are called values. 

Alternatively, you can think of a dictionary as a single row of data from a dataset, where the keys are the variable names.



{:.input_area}
```python
respondent = {'sex'   : "female",
              'abany' : 1,
              'educ'  : 'College'}
```


Dictionaries are surrounded by curly brackets (`{}`). Each entry is pair consisting of the key, which must be a string, followed, by a colon and then the value. Like in a list, entries are seperated by commas.



We can access the contents of a dictionary by enclosing the key in brackets (`[]`).



{:.input_area}
```python
respondent['sex']
```


If the key is not dictionary, you will get a `KeyError`.



{:.input_area}
```python
respondent['gender']
```


You can inspect all the keys in a dictionary, in case you forgot or someone else made it.



{:.input_area}
```python
respondent.keys()
```




{:.input_area}
```python
len(respondent.keys())
```


Dictionaries are mutable, so we can change the value of existing keys, remove keys, or add new ones.



{:.input_area}
```python
respondent['race'] = 'Black'

print(respondent)
```




{:.input_area}
```python
respondent['abany'] = 'Yes'

print(respondent)
```


<div class="alert alert-info">
<h3> Your turn</h3>
<p>Add a new key to the dictionary called <code>age</code> with a value of 37. Confirm that you did it correctly by dispaying the value of <code>age</code>.

</div>


<details>
<summary>Sample answer code</summary> 
<code style="background-color: white">
respondent['age'] = 37
print(respondent['age'])
</code>
</details>

As noted above, while the keys have to be strings, the values can be any data type.



{:.input_area}
```python
respondent['children ages'] = [3, 5, 10]

print(respondent)
```


# Spaces


Within the Python community, there are strong norms about how code should be written. Many of these are centered around have code be readable, both by others and by your future self. As a trivial example, `2+2` is allowed, but is almost always written `2 + 2`. Likewise, I defined my respondent dictionary with plenty of white space to maximize readability.



{:.input_area}
```python
respondent = {'sex'   : "female",
              'abany' : 1,
              'educ'  : 'College'}
```


This is identical to:



{:.input_area}
```python
respondent={'sex':'female','abany':1,'educ':'College'}

```




but putting it all on one line obscures the logic of the dictionary. In this case, what is a key and what is a value is quite clear in the first version, while distinguishing between the two is more problematic in the single-line version. 





{:.input_area}
```python
r2 = {'sex':'male',   'abany':1, 'educ':'College'     }
r3 = {'sex':'female', 'abany':0, 'educ':'High School' }
r4 = {'sex':'male',   'abany':0, 'educ':'Some College'}
```




{:.input_area}
```python
respondents = [respondent, r2, r3, r4]
```




{:.input_area}
```python
respondents
```


This now looks a lot like the common data format JSON!

# Loops



{:.input_area}
```python
for person in respondents:
    print(person['educ'])
```




{:.input_area}
```python
for item in [1,2,'bobcat']:
    print(item)
```



<div class="alert alert-info">
<h3> Your turn</h3>
<p> Loop over the items in your <code>food</code> list. For each item, print its length.

</div>



<details>
<summary>Sample answer code</summary> 
<code style="background-color: white">
for item in food:
    item_len = len(item)
    print(item_len)
</code>
</details>



# Functions

For those who come from Stata or R background, one of the more striking aspects of Python code is the frequency of user-defined functions. These functions are deployed both for cases where you are surprised that no one has already written a function, such as counting words in a sentence, and for highly-custom situations, such as scraping the contents of a particular web page.   Programming with many small functions tends to make code more readable and easier to debug than code written in a more traditional social science style.

A standard function has three parts. First, the function is named. Subsequent lines or lines do the thing. Finally, the results are returned.  

A trivial function that returns the `Hello!` might look like:



{:.input_area}
```python
def make_hello():
    word = 'Hello!'
    return word
```


Of note, `def` signals that your are defining a function. This is followed by the name of the function. In this case, `make_hello`. Since this function doesn't take any arguments, such as accepting a variable to modify or have any options, it is followed by `()`. The first line ends with a colon.

All subsequent lines are indented. The second line creates a new string variable called `word` which contains `Hello!`. The third and final line of the functions returns the value stored in word. 



{:.input_area}
```python
make_hello()
```


More commonly in text analysis, a user-defined function modifies an existing string. In this case, the variable name that will be used within the function is established within the parenthesis on the opening line. 

A second trivial function takes a text string and returns an all-caps version. 



{:.input_area}
```python
def scream(text):
    text_upper = text.upper()
    return text_upper
```




{:.input_area}
```python
scream('Hi there!')
```


![](https://raw.githubusercontent.com/nealcaren/UiOBigData/master/notebooks/images/function.png)

The `text` and `text_upper` variable only exist within the function. That means that you can pass a variable not called `text` to the function.



{:.input_area}
```python
scream(sentence)
```


It also means that everything but the returned `text` disappears.



{:.input_area}
```python
text_upper
```


It is a good idea to include a comment within the function that explains the function. This is helpful for other people reading your code and when you return to your own code months and days later.



{:.input_area}
```python
def scream(text):
    '''Returns an all-caps version of text string.'''
    text_upper = text.upper()
    return text_upper
```


<div class="alert alert-info">
<h3> Your turn</h3>
<p> Make a function call "whisper" that replaces all exclamation marks with a period and returns a lower case version of a string. Test it out.
</div>



{:.input_area}
```python
def whisper(text):
    ''''''
    
    return quiet_text
```


<details>
<summary>Sample answer code</summary> 
<code style="background-color: white">
def whisper(text):
    '''Lower case string and replace
       ! with .'''
    quiet_text = text.replace('!','.')
    quiet_text = quiet_text.lower()
    return quiet_text
</code>

Testing it out:
<code style="background-color: white">
whisper('ASDFASDFAS!')
    
</details>

Congratulations! You've now been introduced to the basics of Python for social scientists.
