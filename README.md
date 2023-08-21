ReGeX | Pads are soft and easy u fool
-----------

## To remove only numbers from a text

**Find what:**
```
  [0-9]+
```
**Replace with:** field empty.

#### Explanation of the regular expression `[0-9]+`:

- [0-9]: This matches any single digit.
- +: This quantifier matches one or more occurrences of the preceding character or group, in this case, digits.


## To add "text" to the beginning of every line in a text

**Find what:**
```
^(.+)$
```
**Replace with:** 
```
YOURTEXT\1
```

#### Explanation of the regular expression `^(.+)$`:

- ^: Anchors the match to the beginning of a line.
- (.+): Captures one or more characters (any character except line breaks) in a group.
- $: Anchors the match to the end of a line.

#### Explanation of the replacement pattern `YOURTEXT\1`:

- text: The string you want to add to the beginning of each line.
- \1: Refers to the first capturing group (the entire line in this case).


## To add "text" to the beginning of every line in a text

**Find what:**
```
.*YOURTEXT.*[\r]?[\n]
```
**Replace with:** field empty.

### Explanation of the regular expression `.*YOURTEXT.*[\r]?[\n]`:

- .*: Matches any sequence of characters.
- YOURTEXT: The specific text you're searching for. Replace it with the text you want to match.
- .*: Matches any sequence of characters.
- [\r]?: Optionally matches a carriage return (CR, \r).
- [\n]: Matches a line feed (LF, \n).

