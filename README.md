# Dictionaries lab

Fork and clone this repo. On your fork, answer and commit the follow questions. When you are finished, submit the link to your repo on Canvas.


## Question 1

- Create an instance of a dictionary called `citiesDict` that maps 3 countries to their capital cities.

- Add two more countries to your dictionary.

- Translate at least 3 of the capital names into another language.

Answer:
```swift
//- Create an instance of a dictionary called `citiesDict` that maps 3 countries to their capital cities.
var citiesDict:[String:String] = ["USA":"Washington DC", "China":"Beijing", "South Korea":"Seoul"]

//- Add two more countries to your dictionary.
citiesDict["France"] = "Paris"
citiesDict["Spain"] = "Madrid"

//- Translate at least 3 of the capital names into another language.
var translateToChinese = citiesDict.updateValue("马德里", forKey: "Spain")
translateToChinese = citiesDict.updateValue("北京", forKey: "China")
translateToChinese = citiesDict.updateValue("汉城", forKey: "Korea")

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

Answer:
```swift
var someDict:[String:Int] = ["One": 1, "Two": 4, "Three": 9, "Four": 16, "Five": 25]

//- Using `someDict`, add together the values associated with "Three" and "Five" and print the result.

var sum = 0
for (key, value) in someDict {
if key == "Three" || key == "Five" {
sum += value
}
}
print(sum)

//- Add values to the dictionary for the keys "Six" and "Seven".

someDict["Six"] = 36
someDict["Seven"] = 49


//- Make a key called `productUpToSeven` and set its value equal to the product of all the values.

var productUpToSeven = 1
for (_, value) in someDict {
productUpToSeven *= value
}
someDict["productUpToSeven"] = productUpToSeven

if let productUpToSeven = someDict["productUpToSeven"] {
print(productUpToSeven)
}

//- Make a key called `sumUpToSix` and set its value equal to the sum of the keys "One", "Two", "Three", "Four", "Five" and "Six".

var sumUpToSix = 0
for (key, value) in someDict {
if key != "Seven" && key != "productUpToSeven" {
sumUpToSix += value
}
}
someDict["sumUpToSix"] = sumUpToSix

if let sumUpToSix = someDict["sumUpToSix"] {
print(sumUpToSix)
}

//- Remove the new keys made in the previous two steps

someDict["productUpToSeven"] = nil
someDict["sumUpToSix"] = nil

//- Add 2 to every value inside of `someDict`.


for (key, value) in someDict {
let newValue = value + 2
someDict[key] = newValue
}
print(someDict)

```

## Question 3

Create a variable that is explicitly typed as a dictionary that maps strings to floating point numbers. Initialize the variable to the data shown in the table below which lists an author name and their comprehensibility score.

| Author Name |    Score |
| :--: | :--: |
| Mark Twain |    8.9 |
| Nathaniel Hawthorne    | 5.1 |
| John Steinbeck    | 2.3 |
| C.S. Lewis | 9.9 |
| Jon Krakauer | 6.1 |

Using the dictionary created in the previous problem, do the following:

- Print out the floating-point score for “John Steinbeck”.

- Add an additional author named “Erik Larson” with an assigned score of 9.2.

- Write an if/else statement that compares the score of John Krakaur with Mark Twain. Print out the name of the author with the highest score.

- Use a for-loop to iterate through the dictionary you created at the beginning of the problem, and print out the content in the form of key: value, one entry per line.

Answer:
```swift
//Create a variable that is explicitly typed as a dictionary that maps strings to floating point numbers. Initialize the variable to the data shown in the table below which lists an author name and their comprehensibility score.
//
//| Author Name |    Score |
//| :--: | :--: |
//| Mark Twain |    8.9 |
//| Nathaniel Hawthorne    | 5.1 |
//| John Steinbeck    | 2.3 |
//| C.S. Lewis | 9.9 |
//| Jon Krakauer | 6.1 |

var authorScoreDict: [String:Double] = ["Mark Twain":8.9,"Nathaniel Hawthorne":5.1,"John Steinbeck":2.3,"C.S. Lewis":9.9,"Jon Krakauer":6.1]

//Using the dictionary created in the previous problem, do the following:
//- Print out the floating-point score for “John Steinbeck”.

if let steinbeckScore = authorScoreDict["John Steinbeck"] {
print(steinbeckScore)
}

//    - Add an additional author named “Erik Larson” with an assigned score of 9.2.

authorScoreDict["Erik Larson"] = 9.2

//    - Write an if/else statement that compares the score of John Krakauer with Mark Twain. Print out the name of the author with the highest score. ***There was a typo here, I added an "e" and removed "h" to John Krakaur***

if let krakauerScore = authorScoreDict["Jon Krakauer"],
let twainScore = authorScoreDict["Mark Twain"] {
if krakauerScore > twainScore {
print("Jon Krakauer")
} else {
print("Mark Twain")
}
}

//- Use a for-loop to iterate through the dictionary you created at the beginning of the problem, and print out the content in the form of key: value, one entry per line.

for (key, value) in authorScoreDict {
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

Answer:
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
"z" : "a",
" " : " "
]

var message = "hello world"


for character in message {
for (key, value) in code {
if key == String(character) {
print(value, terminator: "")
}
}
}
print()

//You are also given an `encodedMessage` which contains only lowercase letters and spaces. Use the `code` dictionary to decode the message and print it.
var encodedMessage = "uijt nfttbhf jt ibse up sfbe"

for character in encodedMessage {
for (key, value) in code {
if value == String(character) {
print(key, terminator: "")
}
}
}
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
```
Answer:
```swift
var firstNames = [String]()

for (index, dict) in people.enumerated() {
for key in dict.keys {
if key == "firstName" {
if let firstNameUnwrapped = people[index][key] {
firstNames.append(firstNameUnwrapped)
}
}
}
}
print(firstNames)
```

Now, create an array of strings called `fullNames` that contains the values for `“firstName”` and `“lastName”` from the dictionary separated by a space.

Answer:
```swift
var fullNames = [String]()

for (index, dict) in people.enumerated() {
for key in dict.keys {
if key == "firstName" {
if  let firstName = people[index]["firstName"],
let lastName = people[index]["lastName"] {
fullNames.append("\(firstName) \(lastName)")
}
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
Answer:
```swift
var bestScore = 0

for dict in peopleWithScores {
for (key, value) in dict {
if key == "score" {
if let score = Int(value) {
if score > bestScore {
bestScore = score
}
}
}
}
}

var bestScoreString = String(bestScore)

for (index, dict) in peopleWithScores.enumerated() {
for value in dict.values {
if value == bestScoreString {
if  let firstName = peopleWithScores[index]["firstName"],
let lastName = peopleWithScores[index]["lastName"] {
print("\(firstName) \(lastName)")
}
}
}
}
```


Print out the dictionary above in the following format:  **full name - score**
Answer:
```swift
var fullNamesWithScores = [String]()

for (index, dict) in peopleWithScores.enumerated() {
for key in dict.keys {
if key == "firstName" {
if  let firstName = peopleWithScores[index]["firstName"],
let lastName = peopleWithScores[index]["lastName"],
let score = peopleWithScores[index]["score"] {
fullNamesWithScores.append("**\(firstName) \(lastName) - \(score)**")
}
}
}
}
print(fullNamesWithScores)
```

## Question 7

`var numbers = [1, 2, 3, 2, 3, 5, 2, 1, 3, 4, 2, 2, 2]`

You are given an array of integers. The frequency of a number is the number of times it appears in the array. Find out the frequency of each one.

Answer:
```swift
//var freqDict: [Int:Int] = [:] 
//
//for number in numbers {
//    if freqDict.keys.contains(number) {
//        freqDict.updateValue(freqDict[number]! + 1, forKey: number)
//    } else {
//        freqDict[number] = 1
//    }
//}
//print(freqDict)
```

Print the numbers in ascending order followed by their frequency.
Answer:
```swift

var newArray = [Int]()

for key in freqDict.keys {
newArray.append(key)
}

var sortedArray = newArray.sorted()
for number in sortedArray {
print("\(number) \(freqDict[number]!)")
}
```

## Question 8

Print the most common letter in the string below:

`var myString = "We're flooding people with information. We need to feed it through a processor. A human must turn information into intelligence or knowledge. We've tended to forget that no computer will ever ask a new question."`

Answer:
```swift
var myString = "We're flooding people with information. We need to feed it through a processor. A human must turn information into intelligence or knowledge. We've tended to forget that no computer will ever ask a new question."

var charArray = Array(myString)
var charDict: [Character:Int] = [:]
var letters = "abcdefghijklmnopqrstuvwxyz"

for character in charArray {
if letters.contains(character) {

if charDict.keys.contains(character) {
charDict.updateValue(charDict[character]! + 1, forKey: character)
} else {

charDict[character] = 1
}
}
}
//print(charDict)

var frequency = 0
var letter = String()

for (key, value) in charDict {
if value > frequency {
frequency = value
letter = String(key)
}
}
print(letter)
```

## Question 9

Write code that creates a dictionary where the keys are Ints between 0 and 20 inclusive, and each key's value is its cube.

Answer:
```swift
var newDict = [Int:Int]()


for i in 0...20 {
newDict[i] = i*i*i
}

print(newDict)
```

## Question 10

Write code that iterates through `testStates` and prints out whether or not that key is in `statePop`.

```swift
let statePop = ["Alabama": 4.8, "Alaska": 0.7, "Arizona": 6.7, "Arkansas": 3.0]
let testStates = ["California","Arizona", "Alabama", "New Mexico"]
```
Answer:
```swift
let statePop = ["Alabama": 4.8, "Alaska": 0.7, "Arizona": 6.7, "Arkansas": 3.0]
let testStates = ["California","Arizona", "Alabama", "New Mexico"]
var newArray = [String]()

for state in statePop.keys {
if testStates.contains(state) {
newArray.append(state)
}
}

for state in testStates {
if newArray.contains(state) {
print("\(state) is a test state.")
} else {
print("\(state) is not a test state.")
}
}
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

Answer:
```swift
var deposits: [String: [Double]] = [
"Williams" : [300.65, 270.45, 24.70, 52.00, 99.99],
"Cooper" : [200.56, 55.00, 600.78, 305.15, 410.76, 35.00],
"Davies" : [400.98, 56.98, 300.00],
"Clark" : [555.23, 45.67, 99.95, 80.76, 56.99, 46.50, 265.70],
"Johnson" : [12.56, 300.00, 640.50, 255.60, 26.88]
]

//a) Write code to to print the name and total amount deposited of the person who recieved the most money.
var sum = 0.0

for (name, array) in deposits {
for money in array {
sum += money

}
print(name,sum)
}

//b) Create an array called `stolenCents`, iterate over deposits for each person and steal their cents! ... like Office Space or Superman 3. Calculate the decimal part of each value, add it to the `stolenCents` array and round down the value in the dict.

var stolenCents = [Double]()

for (_, array) in deposits {
for money in array {
let cents = money - floor(money)
stolenCents.append(cents)
}
}
print(stolenCents)


//c) How much money did you steal?
var stolenCentsTotal: Double = 0.0

for cents in stolenCents{
stolenCentsTotal += cents
}
print("I stole \(Int(floor(stolenCentsTotal*100))) cents.")
```

## Question 12

Print the second most common letter in the string below:

`var myString = "We're flooding people with information. We need to feed it through a processor. A human must turn information into intelligence or knowledge. We've tended to forget that no computer will ever ask a new question."`

```swift
var myString = "We're flooding people with information. We need to feed it through a processor. A human must turn information into intelligence or knowledge. We've tended to forget that no computer will ever ask a new question."

var charArray = Array(myString)
var charDict: [Character:Int] = [:]
var letters = "abcdefghijklmnopqrstuvwxyz"

for character in charArray {
if letters.contains(character) {

if charDict.keys.contains(character) {
charDict.updateValue(charDict[character]! + 1, forKey: character)
} else {

charDict[character] = 1
}
}
}
//print(charDict)

var frequency = 0
var secondFrequency = 0
var mostFreqLetter = String()
var secondFreqLetter = String()

for (key, value) in charDict {
if value > frequency {
frequency = value
mostFreqLetter = String(key)
}

}

for (key, value) in charDict {
if value > secondFrequency && value < frequency {
secondFrequency = value
secondFreqLetter = String(key)
}
}

print(secondFreqLetter,secondFrequency)
```

## Question 13***

Given the below 4 arrays of Ints,

a) create a new array, sorted in ascending order, that contains all the values without duplicates.

b) create another new array that contains unique values that appear in all 4 arrays.

```swift
let arr1 = [2, 4, 5, 6, 8, 10, 12]
let arr2 = [1, 2, 3, 4, 5, 6]
let arr3 = [5, 6, 7, 8, 9, 10, 11, 12]
let arr4 = [1, 3, 4, 5, 6, 7, 9]
```
Answer: (Need help with part b)
```swift
let arr1 = [2, 4, 5, 6, 8, 10, 12]
let arr2 = [1, 2, 3, 4, 5, 6]
let arr3 = [5, 6, 7, 8, 9, 10, 11, 12]
let arr4 = [1, 3, 4, 5, 6, 7, 9]

//a) create a new array, sorted in ascending order, that contains all the values without duplicates.
var newArray = [Int]()
let arrayOfArrays = [arr1,arr2,arr3,arr4]

for array in arrayOfArrays {
for number in array {
if newArray.contains(number) {
continue
}
newArray.append(number)
}
}
print(newArray.sorted())

//b) create another new array that contains unique values that appear in all 4 arrays.
var uniqueArray = [Int]()

for array in arrayOfArrays {
for number in array {
if array.contains(number) {
if uniqueArray.contains(number){
continue
}else{
uniqueArray.append(number)

}
}
}
}
print(uniqueArray)
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
Answer:
```swift
var arrayDOI = declarationOfIndependence.components(separatedBy: CharacterSet.punctuationCharacters).joined().components(separatedBy:.whitespacesAndNewlines)

//print(arrayDOI)

var dictDOI: [String:Int] = [:]

for word in arrayDOI {

if dictDOI.keys.contains(word) {
dictDOI.updateValue(dictDOI[word]! + 1, forKey: word)
} else {
dictDOI[word] = 1
}
}

//print(dictDOI)

var highestFreq = 0
var wordMostFreq = String()

for (key, value) in dictDOI where key.count > 5 {
if (value > highestFreq) {
highestFreq = value
wordMostFreq = key
}
}

print(wordMostFreq)
```
