# Regex

Regular expressions (regex) are extremely useful in extracting information from any text by searching for one or more matches of a specific search pattern.

## Basic Topics

### Anchors: ^ and \$

- **^example**: matches any string that _starts with example_
- **example\$**: matches a string that _ends with example_
- **^example\$**: _exact string match_ (starts and ends with example)
- **example**: matches any string that has the text example in it

### Quantifiers: \* + ? and {}

[Try Here](https://regex101.com/r/cO8lqs/1)

- **abc\***: matches a string that has ab _followed by zero or more_ c
- **abc+**: matches a string that has ab _followed by one or more_ c
- **abc?**: matches a string that has ab _followed by zero or one_ c
- **abc{2}**: matches a string that has ab _followed by 2_ c
  1. **abc{2,}**: matches a string that has ab _followed by 2 or more_ c
  2. **abc{2,5}**: matches a string that has ab _followed by 2 up to 5_ c
- **a(bc)\***: matches a string that has a followed by zero or more copies of the sequence bc

### OR operator: | or []

- **a(b|c)**: matches a string that has a _followed by b or c_ (and captures b or c)
- **a[bc]**: same as previous, but without capturing b or c

### Character classes: \d \w \s and .

- **\d**: matches a single character that is a digit
- **\w**: matches a word character (alphanumeric character plus underscore)
- **\s**: matches a whitespace character (includes tabs and line breaks)
- **.**: matches any character

\d, \w and \s also present their negations with \D, \W and \S respectively.

### Grouping

- **a(bc)**: parentheses create a _capturing group with value bc_

### Bracket expressions []

- **[abc]**: matches a string that has either an a or a b or a c (_the same as a|b|c_)
- **[a-c]**: matches a string that has either an a or a b or a c (_the same as a|b|c_)
  1. **[a-fA-F0-9]**: a string that represents a single hexadecimal digit, case insensitively
  2. **[0-9]%**: a string that has a character from 0 to 9 before a % sign
  3. **[^a-za-z]**: a string that has not a letter from a to z or from A to Z. In this case the ^ is used as negation of the expression

### Look-ahead and Look-behind (?=) / (?<=)

- **d(?=r)**: matches a d only _if is followed by_ r, but r will not be part of the overall regex match
- **(?<=r)d**: matches a d only _if is preceded by_ an r, but r will not be part of the overall regex match

Exercises

    1) Match: abcdefg
              abcd
              abc

    Solution:


    2) Match:  cat.
               896.
               ?=+.
       Skip:   abc1

    Solution:


    3) Match:   can
                man
                fan
       Skip:    dan
                ran
                pan

    Solution:


    4) Match: hot
              dog
       Skip:  bog

    Solution:


    5) Match: Ana
              Bob
              Cpc
       Skip:  aax
              bby
              ccz

    Solution:


    6) Match: wazzzzzup
              wazzzup
       Skip:  wazup

    Solution:


    7) Match: aaaabcc
              aabbbbc
              aacc
       Skip:  a

    Solution:


    8) Match: 1 file found?
              24 files found?
       Skip:  No files found.

    Solution:


    9) Match: 1.   abc
              2.    abc
              3.           abc
       Skip:  4.abc

    Solution:


    10) Match: Mission: successful	Success
        Skip:  Last Mission: unsuccessful	To be completed
               Next Mission: successful upon capture of target

    Solution:


    11) Match: file_record_transcript.pdf	Group: file_record_transcript
               file_07241999.pdf	        Group: file_07241990
        Skip:  testfile_fake.pdf.tmp

    Solution:


    12) Match: Jan 1987	Groups: Jan 1987     1987
               May 1969      	May 1969     1969
               Aug 2011         Aug 2011     2011

    Solution:


    13) Match: 1280x720	 Groups 1280  720
               1920x1600	    1920  1600
               1024x768	        1024  768

    Solution:


    14 Match: 	I love cats
                I love dogs
       Skip: 	I love logs
                I love cogs

    Solution:


    15) Match: The quick brown fox jumps over the lazy dog.	To be completed
               There were 614 instances of students getting 90.0% or above.	To be completed
               The FCC had to censor the network for saying &$#*@!.

    Solution:
