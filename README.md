# EX-11 :Huffman-Coding
## Aim
To implement Huffman coding to compress the data using Python.

## Software Required
1. Anaconda - Python 3.7

## Algorithm:
## Step1:
Get the input String

## Step2:
Create tree nodes

## Step3:
Main function to implement huffman coding

## Step4:
Calculate frequency of occurrence

## Step5:
Print the characters and its huffmancode

 
## Program:
```
Developed By : Ashwin Akash M
Reference Number:212223230024
```
## Get the input String
```
input_string = "Ashwin Akash"
```

# Calculate the frquency of each character
```
frequency = {}
for char in input_string:
    if char in frequency:
        frequency[char] += 1
    else:
        frequency[char] = 1
```
# Create tree nodes
```
nodes = [[char, freq] for char, freq in frequency.items()]
```
# Implementation of huffman coding
```
while len(nodes) > 1:
    nodes = sorted(nodes, key=lambda x: x[1])
    left = nodes.pop(0)
    right = nodes.pop(0)
 
    new_node = [[left, right], left[1] + right[1]]
    nodes.append(new_node)
huffman_tree = nodes[0]
```
# Generate Huffman Code
```
huffman_codes = {}

def generate_codes(tree, code=""):
    if isinstance(tree[0], str):  # If it's a leaf node
        huffman_codes[tree[0]] = code
    else:  
        generate_codes(tree[0][0], code + "0")
        generate_codes(tree[0][1], code + "1")

generate_codes(huffman_tree)
```

# Print the characters and its huffmancode

```print("Character | Huffman Code")
print("-------------------------")
for char, code in huffman_codes.items():
    print(f"    {char}    |    {code}")
```

## Output:

### Print the characters and its huffmancode

![Screenshot 2024-11-16 123155](https://github.com/user-attachments/assets/7f36d5a6-c4c0-497c-909e-3d95320b984e)

## Result
Thus the huffman coding was implemented to compress the data using python programming.
