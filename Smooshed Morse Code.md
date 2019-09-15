# Challenge #380 -- "Smooshed Morse Code"
**Difficulty:** EASY

**Source:** [/r/dailyprogrammer](https://www.reddit.com/r/dailyprogrammer/comments/cmd1hb/20190805_challenge_380_easy_smooshed_morse_code_1/)

For the purpose of this challenge, Morse code represents every letter as a sequence of 1-4 characters, each of which is either `.` (dot) or `-` (dash). The code for the letter `a` is `.-`, `b` is `-...`, etc. The codes for each letter were given.

Normally, you would indicate where one letter ends and the next begins, for instance with a space between the letters' codes, but for this challenge, just smoosh all the coded letters together into a single string consisting of only dashes and dots.

**Examples**:

<code>
smorse("sos") => "...---..."</code><br><code>smorse("daily") => "-...-...-..-.--"</code><br><code>smorse("programmer") => ".--..-.-----..-..-----..-."</code><br><code>smorse("bits") => "-.....-..."</code><br><code>smorse("three") => "-.....-..."
</code><br><br>
An obvious problem we encounter is that decoding is ambiguous. For instance, `bits` and `three` encode to the same string, so you can't tell which one you would decode to without more information.

### My Code

<code>def encode_morse(word)</code><br>
<code>&#160;morse = ".- -... -.-. -.. . ..-. --. .... .. .--- -.- .-.. -- -. --- .--. --.- .-. ... - ..- ...- .-- -..- -.-- --.."</code><br>
<code>&#160;alphabet = "abcdefghijklmnopqrstuvwxyz'</code><br>
<code>&#160;morse_arr = morse.split(" ")</code><br>
<code>&#160;alpha_arr = alphabet.split("")</code><br>
<code>&#160;h = Hash[alpha_arr.zip morse_arr]</code><br>
 <br> 
<code>&#160;word.downcase.split('').each { |m|</code><br>
<code>&#160;&#160;print h[m]</code><br>
<code>&#160;}</code><br>
<code>end</code>
