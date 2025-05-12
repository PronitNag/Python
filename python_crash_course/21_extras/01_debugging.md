# Python में Debugging कैसे करें

## Introduction

Debugging एक ऐसा process है जिसमें हम program के errors को 
identify और fix करते हैं। Iss tutorial में, hum python में 
debugging के different tarike seekhenge.

## 1. Print Statements का Use

Sabse simple debugging technique है print statements का use karna.

```python
def add_numbers(a, b):
    print(f"Adding {a} and {b}")  # Check input values
    result = a + b
    print(f"Result is {result}")  # Check output
    return result

sum_result = add_numbers(5, "7")  # This will cause an error
```

Error output:
```
Adding 5 and 7
Traceback (most recent call last):
  File "debug_example.py", line 7, in <module>
    sum_result = add_numbers(5, "7")
  File "debug_example.py", line 3, in add_numbers
    result = a + b
TypeError: unsupported operand type(s) for +: 'int' and 'str'
```

Humne print statements se dekha ki function ko 5 aur "7" (ek string)
mila, jo error ka reason hai.

## 2. Python Debugger (pdb) का Use

Python ka built-in debugger 'pdb' bahut powerful hai.

```python
import pdb

def calculate_average(numbers):
    pdb.set_trace()  # Debugger will stop here
    total = 0
    for num in numbers:
        total += num
    return total / len(numbers)

# Function call with a list containing a string
calculate_average([10, 20, 30, "40"])
```

PDB commands:
- `n` - next line
- `c` - continue execution
- `p variable_name` - print variable value
- `q` - quit debugger

## 3. Try-Except Blocks का Use

Try-except blocks errors ko handle karne ke liye best hai.

```python
def divide_numbers(a, b):
    try:
        result = a / b
        return result
    except ZeroDivisionError:
        print("Error: Division by zero!")
        return None
    except TypeError as e:
        print(f"Error: {e}")
        return None

# Testing with different inputs
print(divide_numbers(10, 2))    # Works fine
print(divide_numbers(10, 0))    # Division by zero
print(divide_numbers("10", 2))  # Type error
```

Output:
```
5.0
Error: Division by zero!
None
Error: unsupported operand type(s) for /: 'str' and 'int'
None
```

## 4. Logging का Use

Print statements की jagah logging better option hai.

```python
import logging

# Configure logging
logging.basicConfig(
    level=logging.DEBUG,
    format='%(asctime)s - %(levelname)s - %(message)s'
)

def process_data(data):
    logging.debug(f"Processing data: {data}")
    
    if not isinstance(data, list):
        logging.error("Data must be a list")
        return None
    
    try:
        result = [item * 2 for item in data]
        logging.info(f"Processing complete. Result: {result}")
        return result
    except Exception as e:
        logging.exception(f"Error processing data: {e}")
        return None

# Test with different inputs
process_data([1, 2, 3])
process_data("not a list")
process_data([1, 2, "3"])
```

## 5. Assertions का Use

Assertions code mein conditions verify karne mein help karte hain.

```python
def get_user_age(age):
    assert isinstance(age, (int, float)), "Age must be a number"
    assert age >= 0, "Age cannot be negative"
    
    return f"User is {age} years old"

try:
    print(get_user_age(25))     # Works fine
    print(get_user_age(-5))     # Will raise assertion error
except AssertionError as e:
    print(f"Error: {e}")
```

## 6. Debugging Complex Functions

Ek complex function ko debug karne ka example:

```python
def calculate_statistics(data):
    """Calculate mean, median and mode for given data."""
    # Debug: Check input
    print(f"Input data: {data[:5]}... (total: {len(data)} items)")
    
    try:
        # Calculate mean
        total = sum(data)
        count = len(data)
        mean = total / count
        print(f"Debug: Mean calculation - {total}/{count} = {mean}")
        
        # Calculate median
        sorted_data = sorted(data)
        mid_point = count // 2
        
        if count % 2 == 0:
            median = (sorted_data[mid_point-1] + sorted_data[mid_point]) / 2
        else:
            median = sorted_data[mid_point]
        
        print(f"Debug: Median is {median}")
        
        # Calculate mode
        frequency = {}
        for item in data:
            if item in frequency:
                frequency[item] += 1
            else:
                frequency[item] = 1
                
        mode = max(frequency, key=frequency.get)
        print(f"Debug: Mode is {mode} (appears {frequency[mode]} times)")
        
        return {
            "mean": mean,
            "median": median,
            "mode": mode,
            "frequency": frequency
        }
        
    except Exception as e:
        print(f"Error occurred: {str(e)}")
        return None

# Test with sample data
sample_data = [4, 1, 3, 5, 2, 5, 6, 7, 5, 8]
result = calculate_statistics(sample_data)
print(f"Final result: {result}")
```

## 7. Debugging ke liye VS Code Use Karna

VS Code me debugging karne ke liye:

1. Breakpoints lagayen (line number par click karke)
2. Debug menu se "Start Debugging" select karein
3. Variables, call stack, aur watch window check karein

## 8. Unit Tests for Debugging

Unit tests bugs ko early identify karne mein help karte hain.

```python
import unittest

def is_prime(n):
    """Check if a number is prime."""
    if n <= 1:
        return False
    if n <= 3:
        return True
    
    if n % 2 == 0 or n % 3 == 0:
        return False
    
    i = 5
    while i * i <= n:
        if n % i == 0 or n % (i + 2) == 0:
            return False
        i += 6
    
    return True

class TestPrimeFunctions(unittest.TestCase):
    
    def test_prime_numbers(self):
        """Test known prime numbers."""
        primes = [2, 3, 5, 7, 11, 13, 17, 19, 23, 29]
        for num in primes:
            self.assertTrue(is_prime(num), f"{num} should be prime")
    
    def test_non_prime_numbers(self):
        """Test known non-prime numbers."""
        non_primes = [1, 4, 6, 8, 9, 10, 12, 14, 15]
        for num in non_primes:
            self.assertFalse(is_prime(num), f"{num} should not be prime")

if __name__ == "__main__":
    unittest.main()
```

## Conclusion

Python mein debugging multiple tarike se ki ja sakti hai. Good
programmers alag-alag situations ke liye sahi technique choose
karte hain. Regular debugging practice se aap better code likhenge
aur problems jaldi solve kar payenge.

Happy debugging!
