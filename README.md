# UTF8 Code Point

**Python library** to make and get the encoding of unicode code points in UTF8.

## tables of rules for encoding UTF8

Design UTF-8 can be seen in the following table that originally 
proposed by *Dave Prosser* and subsequently modified by *Ken Thompson*. You 
can read more on the table above in https://en.wikipedia.org/wiki/UTF-8

<<<<<<< HEAD
<<<<<<< HEAD
## How To Install
```
$ pip install utf8_docepoint
```
=======
You can read more on the table above in https://en.wikipedia.org/wiki/UTF-8
>>>>>>> 66663ffc166f5809406c577e26392e73c125912d
=======
You can read more on the table above in https://en.wikipedia.org/wiki/UTF-8
>>>>>>> 66663ffc166f5809406c577e26392e73c125912d

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
