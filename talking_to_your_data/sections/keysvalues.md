# Keys and Values

A common task in data science and programming more broadly is looking up data. One technique for looking up data we've learned previously is slicing. In slicing, we provide an integer that corresponds to the location of an item in a list.

Another way to look up data is through a key and value pair, in which a key (a label) is used to access a value (a piece of data).

## Dictionaries

A dictionary is a data type that allows you to provide a key (a unique label) for looking up a value (a piece of data). 

Try entering the following to create a phone book in the form of a dictionary. (If you've never used a phone book before, they allowed you to look up a phone number based on a person's name.)

```python
phone_book = {
    "Patrick": 9999999999,
    "Sarah": 3333333333,
    "Guido": 5555555555,
}
```

[Link to instructions for entering this code character by character](typing_instructions/dictionary.md)

The syntax for a dictionary is as follows:

- The dictionary opens and closes with curly braces. On an English keyboard, these characters are on the same key as the square bracket, and require you to hold `Shift`.
- Dictionary keys are most commonly either an integer or a string.
- Dictionary values can be any data type.
- The key is seperated from the value with a `:` (a colon). 
- Each key-value pair is separated from the next with a comma.

## Looking Up Data in a Dictionary

To look up data in our dictionary, we use the following syntax:

```python
phone_book["Patrick"]
```

That's our dictionary variable, then an opening square bracket, then the key as a string, then a closing bracket.

The output of the above should be our value, in this case `9999999999`.




