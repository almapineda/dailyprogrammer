# Challenge #380 -- "Smooshed Morse Code"
**Difficulty:** EASY
**Source:** [/r/dailyprogrammer](https://www.reddit.com/r/dailyprogrammer/comments/cmd1hb/20190805_challenge_380_easy_smooshed_morse_code_1/)

For the purpose of this challenge, Morse code represents every letter as a sequence of 1-4 characters, each of which is either `.` (dot) or `-` (dash). The code for the letter `a` is `.-`, `b` is `-...`, etc. The codes for each letter were given.

Normally, you would indicate where one letter ends and the next begins, for instance with a space between the letters' codes, but for this challenge, just smoosh all the coded letters together into a single string consisting of only dashes and dots.

**Examples**:
`smorse("sos") => "...---..."

smorse("daily") => "-...-...-..-.--"

smorse("programmer") => ".--..-.-----..-..-----..-."

smorse("bits") => "-.....-..."

smorse("three") => "-.....-..."`

An obvious problem we encounter is that decoding is ambiguous. For instance, `bits` and `three` encode to the same string, so you can't tell which one you would decode to without more information.

### My Code

`def encode_morse(word)
  morse = ".- -... -.-. -.. . ..-. --. .... .. .--- -.- .-.. -- -. --- .--. --.- .-. ... - ..- ...- .-- -..- -.-- --.."
  alphabet = 'a b c d e f g h i j k l m n o p q r s t u v w x y z'
  morse_array = morse.split(' ')
  alpha_array = alphabet.split(' ')
  h = Hash[alpha_array.zip morse_array]

  word.downcase.split('').each { |m|
    print h[m]
  }
end`
