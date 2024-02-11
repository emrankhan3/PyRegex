# PyRegex

## Raw String
Raw string in python a string prefix with an r
```py
print('\tTab')
#output
#---->Tab
```
vs
```py
print(r'\tTab')
#output
#\tTab
```

## python Regex
```py
.		- Any Character Except New Line
\d		- Digit (0-9)
\D		- Not a Digit (0-9)
\w		- Word Character (a-z, A-Z, 0-9, _)
\s		- Whitespace (space, tab, newline)
\S		- Not \s

..........anchors=============
\b		- Word Boundary

\B		- Not a Word Boundary
^		- Beginnig of a String
$		- End of a String
"this is"
'\bis'  will match is
'\Bis will match is inside this

'Start with Start end of the End'

'^Start' will match first 'Start'
'End$' will match the last 'End'

[] --- character set, only match single character satisfy the condition with in []
if we use '^' inside [], then char except inside [] will satisfy the condition

e.g:
r'[^a-zA-Z]' will match anything except a-z and A-Z

r'[^b]at'    will match cat, rat, hat anything but not 'bat'

Quantifiers:

- `-> 0 or More`
- `-> 1 or More`

?		-> 0 or One
{3}		-> exact Number
{3,4}		-> range of number {min,max}

Group:
()
r'M(r|s|rs).?\s[A-Z]\w*
Mr. Schefar
Mrs. Bson
Ms Kast
Mr. T

###Sample Regexs ####

email = '''
[CoreMSchafer@gmail.com](mailto:CoreMSchafer@gmail.com)[corey.schafer@university.edu](mailto:corey.schafer@university.edu)[corey-321-schafer@my-work.net](mailto:corey-321-schafer@my-work.net)
'''
pat = re.compile(r'\w+@gmail.com')

# r'[a-zA-Z]+@[a-zA-Z]+'

#p2 =  re.compile(r'\w+@\w+')
for m in p2.finditer(email):
print(m)
output:
<re.Match object; span=(1, 19), match='CoreMSchafer@gmail'>
<re.Match object; span=(30, 48), match='schafer@university'>
<re.Match object; span=(63, 73), match='schafer@my'>

p3 = re.compile(r'[a-zA-Z.-0-9]+@[a-zA-Z-.]+\.(com|edu|net)')
for m in p3.finditer(email):
print(m)
<re.Match object; span=(1, 23), match='CoreMSchafer@gmail.com'>
<re.Match object; span=(24, 52), match='corey.schafer@university.edu'>
<re.Match object; span=(62, 82), match='-schafer@my-work.net'>

p4 = re.compile(r'[a-zA-Z0-9.+-]+@[a-zA-Z0-9-]+\.[a-zA-Z0-9-.]+')
for m in p4.finditer(email):
print(m)

pat = re.compile(r'\w+@gmail.com')
#r'[a-zA-Z]+@[a-zA-Z]+'
p2 =  re.compile(r'\w+@\w+')
p3 = re.compile(r'[a-zA-Z.-0-9]+@[a-zA-Z-.]+\.(com|edu|net)')
p4 = re.compile(r'[a-zA-Z0-9.+-]+@[a-zA-Z0-9-]+\.[a-zA-Z0-9-.]+')
p5 = re.compile(r'https?://[a-zA-Z.0-9]+\.com[0-9a-zA-Z/]*')
p6 = re.compile(r'')
pcurl = re.compile(r'https?://(www\.)?\w+\.\w+')
pcurlG = re.compile(r'https?://(www\.)?(\w+)\.(\w+)')
for m in pcurlG.finditer(urls):
print(m.group())

== findall() ===
```
ref: https://www.youtube.com/watch?v=K8L6KVGG-7o
