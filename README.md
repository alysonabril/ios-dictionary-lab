# Dictionaries lab

Fork and clone this repo. On your fork, answer and commit the follow questions. When you are finished, submit the link to your repo on Canvas.


## Question 1

- Create an instance of a dictionary called `citiesDict` that maps 3 countries to their capital cities.

- Add two more countries to your dictionary.

- Translate at least 3 of the capital names into another language.
```swift
var citiesDict = ["Colombia": "Bogota", "Ecuador": "Quito", "England": "London"]

citiesDict["France"] = "Paris"
citiesDict["Italy"] = "Rome"
print(citiesDict)

citiesDict["France"] = "باريس"//arabic
citiesDict["Italy"] = "روما"//arabic
citiesDict["England"] = "لندن"//arabic
print(citiesDict)

```

## Question 2

`var someDict:[String:Int] = ["One": 1, "Two": 4, "Three": 9, "Four": 16, "Five": 25]`

- Using `someDict`, add together the values associated with "Three" and "Five" and print the result.

- Add values to the dictionary for the keys "Six" and "Seven".

- Make a key called `productUpToSeven` and set its value equal to the product of all the values.

- Make a key called `sumUpToSix` and set its value equal to the sum of the keys "One", "Two", "Three", "Four", "Five" and "Six".

- Remove the new keys made in the previous two steps

- Add 2 to every value inside of `someDict`.
```swift

var someDict:[String:Int] = ["One": 1, "Two": 4, "Three": 9, "Four": 16, "Five": 25]
// Using `someDict`, add together the values associated with "Three" and "Five" and print the result.

// - Add values to the dictionary for the keys "Six" and "Seven".
someDict["six"] = 1
someDict["seven"] = 2

// - Make a key called `productUpToSeven` and set its value equal to the product of all the values.
someDict["productUpToSeven"] = someDict.values.reduce(1, *)

//- Make a key called `sumUpToSix` and set its value equal to the sum of the keys "One", "Two", "Three", "Four", "Five" and "Six". //david said to add sum of values

someDict["sumUpToSix"] = 0
var sumOfSixKeys = 0

for (key, value) in someDict {
if key != "seven"{
sumOfSixKeys += value
}
}
someDict["sumUpToSix"] = sumOfSixKeys

//- Remove the new keys made in the previous two steps
someDict["sumUpToSix"] = nil
someDict["productUpToSeven"] = nil
//- Add 2 to every value inside of `someDict`.

for (key,value) in someDict {
someDict[key] = value + 2
}

print(someDict)

```
## Question 3

Create a variable that is explicitly typed as a dictionary that maps strings to floating point numbers. Initialize the variable to the data shown in the table below which lists an author name and their comprehensibility score.

| Author Name |	Score |
| :--: | :--: |
| Mark Twain |	8.9 |
| Nathaniel Hawthorne	| 5.1 |
| John Steinbeck	| 2.3 |
| C.S. Lewis | 9.9 |
| Jon Krakauer | 6.1 |

Using the dictionary created in the previous problem, do the following:

- Print out the floating-point score for “John Steinbeck”.

- Add an additional author named “Erik Larson” with an assigned score of 9.2.

- Write an if/else statement that compares the score of John Krakaur with Mark Twain. Print out the name of the author with the highest score.

- Use a for-loop to iterate through the dictionary you created at the beginning of the problem, and print out the content in the form of key: value, one entry per line.
```swift


var myAuthorDictionary: [String: Float]
myAuthorDictionary = [
"Mark Twain": 8.9,
"Nathaniel Hawthorne": 5.1,
"John Steinbeck": 2.3,
"C.S. Lewis": 9.9,
"Jon Krakaur": 6.1
]

//- Print out the floating-point score for “John Steinbeck”.
print(myAuthorDictionary["John Steinbeck"] ?? "no comprehension score for this author")

//- Add an additional author named “Erik Larson” with an assigned score of 9.2.
myAuthorDictionary["Erik Larson"] = 9.2

//- Write an if/else statement that compares the score of John Krakaur with Mark Twain. Print out the name of the author with the highest score.
if "John Krakaur" > "Mark Twain" {
print("John Krakaur")
} else {
print("Mark Twain")
}

//Use a for-loop to iterate through the dictionary you created at the beginning of the problem, and print out the content in the form of key: value, one entry per line.

for (key, value) in myAuthorDictionary {
print("\(key): \(value)")
}

```

## Question 4

You are given a dictionary code of type [String:String] which has values for all lowercase letters. The code dictionary represents a way to encode a message. For example if code["a"] = "z" and code["b"] = "x" the encoded version if "ababa" will be "zxzxz". You are also given a message which contains only lowercase letters and spaces. Use the `code` dictionary below to encode the message and print it.

```swift
var code = [
    "a" : "b",
    "b" : "c",
    "c" : "d",
    "d" : "e",
    "e" : "f",
    "f" : "g",
    "g" : "h",
    "h" : "i",
    "i" : "j",
    "j" : "k",
    "k" : "l",
    "l" : "m",
    "m" : "n",
    "n" : "o",
    "o" : "p",
    "p" : "q",
    "q" : "r",
    "r" : "s",
    "s" : "t",
    "t" : "u",
    "u" : "v",
    "v" : "w",
    "w" : "x",
    "x" : "y",
    "y" : "z",
    "z" : "a"
]

var message = "hello world"
```

You are also given an `encodedMessage` which contains only lowercase letters and spaces. Use the `code` dictionary to decode the message and print it.
`var encodedMessage = "uijt nfttbhf jt ibse up sfbe"`

```swift
var message = "hello world"
var codedMessage = ""
var space = " "
//subscript message into two words and then join them
for char in message {
for (key,value) in code {
if String(char) == key {
codedMessage.append(value)
}
}
if String(char) == space {
codedMessage.append(space)
}
}
print(codedMessage)


//You are also given an `encodedMessage` which contains only lowercase letters and spaces. Use the `code` dictionary to decode the message and print it.
var encodedMessage = "uijt nfttbhf jt ibse up sfbe"
var decodedMessage = ""

for char in encodedMessage {
for (key, value) in code {
if String(char) == value {
decodedMessage.append(key)
}
}
if String(char) == space {
decodedMessage.append(space)
}
}
print(decodedMessage)
```
## Question 5

You are given an array of dictionaries. Each dictionary in the array contains exactly 2 keys `“firstName”` and `“lastName”`. Create an array of strings called `firstNames` that contains only the values for `“firstName”` from each dictionary.

```swift
var people: [[String:String]] = [
    [
        "firstName": "Calvin",
        "lastName": "Newton"
    ],
    [
        "firstName": "Garry",
        "lastName": "Mckenzie"
    ],
    [
        "firstName": "Leah",
        "lastName": "Rivera"
    ],
    [
        "firstName": "Sonja",
        "lastName": "Moreno"
    ],
    [
        "firstName": "Noel",
        "lastName": "Bowen"
    ]
]

var firstNames = [String]()

for person in people {
if let firstName = person["firstName"] {
print(firstName)
firstNames.append(firstName)
}
}
```

Now, create an array of strings called `fullNames` that contains the values for `“firstName”` and `“lastName”` from the dictionary separated by a space.

```swift
for person in people {
if let firstName = person["firstName"] {
if let lastName = person["lastName"] {
let fullName = "\(firstName) \(lastName)"
fullNames.append(fullName)
}
}
}
print(fullNames)

```


## Question 6

You are given an array of dictionaries. Each dictionary in the array describes the score of a person. Find the person with the best score and print his full name.

```swift
var peopleWithScores: [[String: String]] = [
    [
        "firstName": "Calvin",
        "lastName": "Newton",
        "score": "13"
    ],
    [
        "firstName": "Garry",
        "lastName": "Mckenzie",
        "score": "23"
    ],
    [
        "firstName": "Leah",
        "lastName": "Rivera",
        "score": "10"
    ],
    [
        "firstName": "Sonja",
        "lastName": "Moreno",
        "score": "3"
    ],
    [
        "firstName": "Noel",
        "lastName": "Bowen",
        "score": "16"
    ]
]
```

Print out the dictionary above in the following format:  **full name - score**
```swift
var bestPerson = ""
var bestScore = 0

for person in peopleWithScores {
for (key, value) in person {
if let intValue = Int(value) {
if key == "score" && intValue > bestScore {
if let firstName = person["firstName"] {
if let lastName = person["lastName"] {
let fullName = "\(firstName) \(lastName)"
bestPerson = fullName
bestScore = intValue
}
}
}
}
}
}

var fullNameAndScore = "\(bestPerson) - \(bestScore)"

print(fullNameAndScore)

```

## Question 7

`var numbers = [1, 2, 3, 2, 3, 5, 2, 1, 3, 4, 2, 2, 2]`

You are given an array of integers. The frequency of a number is the number of times it appears in the array. Find out the frequency of each one.

Print the numbers in ascending order followed by their frequency.
```swift

var numbers = [1, 2, 3, 2, 3, 5, 2, 1, 3, 4, 2, 2, 2]
let mappedItems = numbers.map { ($0, 1) }
let numbersDict = Dictionary(mappedItems, uniquingKeysWith: +)

print(numbersDict)

```

## Question 8

Print the most common letter in the string below:

`var myString = "We're flooding people with information. We need to feed it through a processor. A human must turn information into intelligence or knowledge. We've tended to forget that no computer will ever ask a new question."`

```swift
var letterDictionary: [String: Int] = [:]
var counter = 0

var letter = String()

for char in myString {

if letterDictionary[String(char)] == nil {
letterDictionary[String(char)] = 1
}
letterDictionary[String(char)] = (letterDictionary[String(char)]!) + 1
}

for (key,value) in letterDictionary {
if value > counter && key != " " {
counter = value
letter = key
}
}
print("most common letter: \(letter), it repeats: \(counter) times")

```
## Question 9

Write code that creates a dictionary where the keys are Ints between 0 and 20 inclusive, and each key's value is its cube.

```swift


```
## Question 10

Write code that iterates through `testStates` and prints out whether or not that key is in `statePop`.

```swift
let statePop = ["Alabama": 4.8, "Alaska": 0.7, "Arizona": 6.7, "Arkansas": 3.0]
let testStates = ["California","Arizona", "Alabama", "New Mexico"]
```


## Question 11

You are given the dictionary `deposits`, which maps a persons name to an array of deposits that have been made to their account.

a) Write code to to print the name and total amount deposited of the person who recieved the most money.

b) Create an array called `stolenCents`, iterate over deposits for each person and steal their cents! ... like Office Space or Superman 3. Calculate the decimal part of each value, add it to the `stolenCents` array and round down the value in the dict.

c) How much money did you steal?

```swift
var deposits: [String: [Double]] = [
 "Williams" : [300.65, 270.45, 24.70, 52.00, 99.99],
 "Cooper" : [200.56, 55.00, 600.78, 305.15, 410.76, 35.00],
 "Davies" : [400.98, 56.98, 300.00],
 "Clark" : [555.23, 45.67, 99.95, 80.76, 56.99, 46.50, 265.70],
 "Johnson" : [12.56, 300.00, 640.50, 255.60, 26.88]
]
```


## Question 12

Print the second most common letter in the string below:

`var myString = "We're flooding people with information. We need to feed it through a processor. A human must turn information into intelligence or knowledge. We've tended to forget that no computer will ever ask a new question."`
```swift


```

## Question 13

Given the below 4 arrays of Ints,

a) create a new array, sorted in ascending order, that contains all the values without duplicates.

b) create another new array that contains unique values that appear in all 4 arrays.

```swift
let arr1 = [2, 4, 5, 6, 8, 10, 12]
let arr2 = [1, 2, 3, 4, 5, 6]
let arr3 = [5, 6, 7, 8, 9, 10, 11, 12]
let arr4 = [1, 3, 4, 5, 6, 7, 9]
```


## Question 14

Given the following exert from the Declaration of Independence, find the most frequent word that is longer than 5 characters.

 - use `components(separatedBy:)` to break up the string into an array.

 - use `CharacterSet.punctuationCharacters` in union with any other characters you don't want in your array, like spaces and new lines.

 ```swift
let declarationOfIndependence = """
When in the Course of human events, it becomes necessary for one people to dissolve the
political bands which have connected them with another, and to assume among the powers of the
earth, the separate and equal station to which the Laws of Nature and of Nature's God entitle
them, a decent respect to the opinions of mankind requires that they should declare the causes
which impel them to the separation.

We hold these truths to be self-evident, that all men are created equal, that they are endowed by
their Creator with certain unalienable Rights, that among these are Life, Liberty and the pursuit
of Happiness. That to secure these rights, Governments are instituted among Men, deriving
their just powers from the consent of the governed, That whenever any Form of Government
becomes destructive of these ends, it is the Right of the People to alter or to abolish it, and to
institute new Government, laying its foundation on such principles and organizing its powers in
such form, as to them shall seem most likely to effect their Safety and Happiness. Prudence,
indeed, will dictate that Governments long established should not be changed for light and
transient causes; and accordingly all experience hath shewn, that mankind are more disposed to
suffer, while evils are sufferable, than to right themselves by abolishing the forms to which they
are accustomed. But when a long train of abuses and usurpations, pursuing invariably the same
Object evinces a design to reduce them under absolute Despotism, it is their right, it is their duty,
to throw off such Government, and to provide new Guards for their future security. Such has
been the patient sufferance of these Colonies; and such is now the necessity which constrains
them to alter their former Systems of Government. The history of the present King of Great
Britain is a history of repeated injuries and usurpations, all having in direct object the
establishment of an absolute Tyranny over these States. To prove this, let Facts be submitted to a
candid world.
"""
```
