# 📝 ReGeX | Pads are soft and easy u fool 
-----------

## 📝 To remove only numbers from a text

**Find what:**
```
  [0-9]+
```
**Replace with:** field empty.

#### Explanation of the regular expression `[0-9]+`:

- [0-9]: This matches any single digit.
- +: This quantifier matches one or more occurrences of the preceding character or group, in this case, digits.


## 📝 To add "text" to the beginning of every line in a text

**Find what:**
```
^(.+)$
```
**Replace with:** 
```
YOUR_TEXT\1
```

#### Explanation of the regular expression `^(.+)$`:

- ^: Anchors the match to the beginning of a line.
- (.+): Captures one or more characters (any character except line breaks) in a group.
- $: Anchors the match to the end of a line.

#### Explanation of the replacement pattern `YOUR_TEXT\1`:

- text: The string you want to add to the beginning of each line.
- \1: Refers to the first capturing group (the entire line in this case).

## 📝 To add "YOUR_TEXT" to the ending of every line in a text

**Find what:**
```
^(.+)$
```
**Replace with:** 
```
YOUR_TEXT
```

#### Explanation of the regular expression `^(.+)$`:

- ^: Anchors the match to the beginning of a line.
- (.+): Captures one or more characters (any character except line breaks) in a group.
- $: Anchors the match to the end of a line.

#### Explanation of the replacement pattern `YOUR_TEXT`:

- text: The string you want to add to the beginning of each line.

## 📝 To removes the every line containing "YOUR_TEXT"

**Find what:**
```
.*YOUR_TEXT.*[\r]?[\n]
```
**Replace with:** field empty.

### Explanation of the regular expression `.*YOUR_TEXT.*[\r]?[\n]`:

- .*: Matches any sequence of characters.
- YOUR_TEXT: The specific text you're searching for. Replace it with the text you want to match.
- .*: Matches any sequence of characters.
- [\r]?: Optionally matches a carriage return (CR, \r).
- [\n]: Matches a line feed (LF, \n).

Matching a phone number: `/\d{3}-\d{3}-\d{4}/` matches a phone number in the format of XXX-XXX-XXXX.

Matching an email address: `/\w+@\w+.\w+/` matches an email address in the format of username@domain.com.

Matching a URL: `/^(http|https)://[\w-]+(.[\w-]+)+([\w-.,@?^=%&:/~+#]*)?/` matches a URL in the format of http://www.example.com/page.html.

## 📝 To removes the every line containing numbers

**Find what:**
```
.*[0-9]+.*[\r]?[\n]
```
**Replace with:** field empty.

### Explanation of the regular expression `.*[0-9]+.*[\r]?[\n]`:

- .*: Matches any sequence of characters.
- [0-9]: This matches any single digit.
- +: This quantifier matches one or more occurrences of the preceding character or group, in this case, digits.
- .*: Matches any sequence of characters.
- [\r]?: Optionally matches a carriage return (CR, \r).
- [\n]: Matches a line feed (LF, \n).


## 📝 To remove everything after a "YOUR_TEXT" in each line in Notepad

**Find what:**
```
YOUR_TEXT.*$
```
**Replace with:** 
```
YOUR_TEXT
```

#### Explanation of the regular expression `YOUR_TEXT.*$`:

- `YOUR_TEXT`: Replace this with your specific text.
- `.*`: Matches any sequence of characters.
- `$`: Matches the end of a line.

This regular expression finds the specified text (`YOUR_TEXT`) followed by any characters (`.*`) until the end of the line (`$`). By replacing it with an empty string, it removes everything after `YOUR_TEXT` in each line.


----------------------------------

# Linux tools

### To filter user names.
```
grep -oP '<value>\K[^<]+@example.com(?=</value>)' input.txt | sed 's/@example.com//g' | sort | uniq > outputfiltered.txt
```

