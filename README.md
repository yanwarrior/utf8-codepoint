# UTF8 Code Point

**Python library** to make and get the encoding of unicode code points in UTF8.

## tables of rules for encoding UTF8

Design UTF-8 can be seen in the following table that originally 
proposed by *Dave Prosser* and subsequently modified by *Ken Thompson*. You 
can read more on the table above in https://en.wikipedia.org/wiki/UTF-8

## How To Install
```
$ pip install utf8_codepoint
```


## Example

simple examples using this package.

#### Quick Start

```python
from utf8_codepoint import CodePoint

# unicode symbol for European currency
euro_money = "U+20AC"

# create instance object
cp = CodePoint(euro_money)

# get representation integer of the Unicode Code Point
print(cp.to_int())
```

the result is:


```python
226 130 172
```

#### to a hexadecimal representation

```python
from utf8_codepoint import CodePoint
...	

print(cp.to_hex())
```

the result is:

```python
E2 82 AC
```
	
#### to a string with binary representation

```python
	
from utf8_codepoint import CodePoint
...
	
print(cp.to_string())
```
	
the result is:

```python
11100010 10000010 10101100
```

#### to a list of binary string representation

```python
from utf8_codepoint import CodePoint
...
	
print(cp.to_list())
```

the result is:

```python
['11100010', '10000010', '10101100']
```

#### displays all the data with beautiful style

```python
from utf8_codepoint import CodePoint
...
	
cp.bprint()
```

the result is:

```
{'0x20AC': {'bit_list': ['11100010', '10000010', '10101100'],
        'code_point': 16,
        'hexa_list': ['0xe2', '0x82', '0xac'],
        'initial_bit': '1110',
        'integer_list': [226, 130, 172]}}
        
```
   
**Get all data**

```python

from utf8_codepoint import CodePoint
...
	
print(cp.get_all())
```
	
the result is:

```
{'0x20AC': 
	{
		'bit_list': ['11100010', '10000010', '10101100'], 
		'integer_list': [226, 130, 172], 
		'initial_bit': '1110', 
		'hexa_list': ['0xe2', '0x82', '0xac'], 
		'code_point': 16
	}
}
```

If you want to turn it into a json format, you can pass a 
true value as a parameter in the method get_all:

```python
cp.get_all(True)
```

>>> build with love, provide with sincerity.

#### License

```
Copyright (c) 2015 Yanwar Solahudin

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

```
