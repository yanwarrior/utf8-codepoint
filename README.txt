================
UTF8 Code Point
================

**Python library** to make and get the encoding of unicode code points in UTF8.

tables of rules for encoding UTF8
----------------------------------

Design UTF-8 can be seen in the following table that originally 
proposed by *Dave Prosser* and subsequently modified by *Ken Thompson*.

+------------+------------+------------+---------+
| Bit        | The first  | The last   | Byte in |
| Code Point | code point | code point | Squence |
+------------+------------+------------+---------+
| 7          | U+0000     | U+007F     | 1       |
+------------+------------+------------+---------+
| 11         | U+0080 	  | U+07FF     |  2 	 |
+------------+------------+------------+---------+
| 16 	     | U+0800 	  | U+FFFF     |  3      |
+------------+------------+------------+---------+ 
| 21	     | U+10000    | U+1FFFFF   |  4      |
+------------+------------+------------+---------+ 
| 26         | U+200000   | U+3FFFFFF  |  5      |
+------------+------------+------------+---------+ 	
| 31         | U+4000000  | U+7FFFFFFF |  6      |
+------------+------------+------------+---------+

You can read more on the table above in `a link`_.

.. _a link: https://en.wikipedia.org/wiki/UTF-8

Example
--------

simple examples using this package.

**Quick Start**

::
	
	from utf8_codepoint import CodePoint

	# unicode symbol for European currency
	euro_money = "U+20AC"

	# create instance object
	cp = CodePoint(euro_money)

	# get representation integer of the Unicode Code Point
	print(cp.to_int())

the result is:

::
	
	226 130 172

**to a hexadecimal representation**

::
	
	from utf8_codepoint import CodePoint
	...
	
	print(cp.to_hex())

the result is:

::

	E2 82 AC
	
**to a string with binary representation**

::
	
	from utf8_codepoint import CodePoint
	...
	
	print(cp.to_string())
	
the result is:

::

	11100010 10000010 10101100

**to a list of binary string representation**

::
	
	from utf8_codepoint import CodePoint
	...
	
	print(cp.to_list())

the result is:

::

	['11100010', '10000010', '10101100']


**displays all the data with beautiful style**

::

	from utf8_codepoint import CodePoint
	...
	
	cp.bprint()

the result is:

::

	{'0x20AC': {'bit_list': ['11100010', '10000010', '10101100'],
            'code_point': 16,
            'hexa_list': ['0xe2', '0x82', '0xac'],
            'initial_bit': '1110',
            'integer_list': [226, 130, 172]}}
        
    
**Get all data**

::

	from utf8_codepoint import CodePoint
	...
	
	print(cp.get_all())
	
the result is:

::

	{'0x20AC': 
		{
			'bit_list': ['11100010', '10000010', '10101100'], 
			'integer_list': [226, 130, 172], 
			'initial_bit': '1110', 
			'hexa_list': ['0xe2', '0x82', '0xac'], 
			'code_point': 16
		}
	}

If you want to turn it into a json format, you can pass a 
true value as a parameter in the method get_all:

::

	cp.get_all(True)



	
