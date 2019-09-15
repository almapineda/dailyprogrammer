# Challenge #380 -- "Smooshed Morse Code"
**Difficulty:** EASY

**Source:** [/r/dailyprogrammer](https://www.reddit.com/r/dailyprogrammer/comments/cmd1hb/20190805_challenge_380_easy_smooshed_morse_code_1/)

For the purpose of this challenge, Morse code represents every letter as a sequence of 1-4 characters, each of which is either `.` (dot) or `-` (dash). The code for the letter `a` is `.-`, `b` is `-...`, etc. The codes for each letter were given.

Normally, you would indicate where one letter ends and the next begins, for instance with a space between the letters' codes, but for this challenge, just smoosh all the coded letters together into a single string consisting of only dashes and dots.

**Examples**:

<code>
smorse("sos") => "...---..."

smorse("daily") => "-...-...-..-.--"

smorse("programmer") => ".--..-.-----..-..-----..-."<br>
smorse("bits") => "-.....-..."<br>
smorse("three") => "-.....-..."<br>
</code>

An obvious problem we encounter is that decoding is ambiguous. For instance, `bits` and `three` encode to the same string, so you can't tell which one you would decode to without more information.

### My Code
<code>
def encode_morse(word)<br>
&#160;morse = ".- -... -.-. -.. . ..-. --. .... .. .--- -.- .-.. -- -. --- .--. --.- .-. ... - ..- ...- .-- -..- -.-- --.."<br>
&#160;alphabet = "abcdefghijklmnopqrstuvwxyz'<br>
&#160;morse_arr = morse.split(" ")<br>
&#160;alpha_arr = alphabet.split("")<br>
&#160;h = Hash[alpha_arr.zip morse_arr]<br>
 <br> 
&#160;word.downcase.split('').each { |m|<br>
&#160;&#160;print h[m]<br>
&#160;}<br>
end
</code>
