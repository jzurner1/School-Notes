Regular expressions (RegEx) is a sequence of characters that specify a search pattern in text. It is usually used for finding a pattern or verifying that a string matches a pattern.

# Matching characters
`[a-z]`: Match any letters from a-z
`[^a-z]`: Match anything that is not a-z
`[abc123]`: Match any characters that are a, b, c, 1, 2, or 3.
`[^yz89]`: Match any characters that are not y, z, 8, or 9
`abc`: Match exactly abc
`.`: Match any character except newline
`\w`: Match any word character (alphanumeric and underscore)
`\W`: Match anything except word characters
`\d`: Match any digit
`\D`: Match anything except digits
`\s`: Match any whitespace (spaces, tabs, line breaks)
`\S`: Match anything except whitespace
`\uFFFF`: Match a unicode character from its four character code
`\xFF`: Match a hexadecimal character from its two character code
`x|y`: Match either x or y

# Quantifiers
Quantifiers refer to the number of the previous token
`*`: Match 0 or more of the previous token
`+`: Match 1 or more of the previous token
`?`: Match 0 or 1 of the previous token
`{x}`: Match exactly x of the previous token
`{x,}`: Match x or more of the previous token
`{x,y}`: Match between x and y of the previous token
`+?`: Match as few of the previous tokens as possible, make it lazy