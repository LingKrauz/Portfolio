# Algorithm for File Updates in Python

## Project Description
This algorithm demonstrates how to use Python to open a list of IP addresses, remove specified IP addresses, then save and close the file.

---

## Steps

### 1. **Open the file that contains the allow list**
```python
# Build `with` statement to read in the initial contents of the file

with open(import_file, "r") as file:
```
This `with` statement opens the file stored in the variable `import_file`, which is passed in as an argument in the function we create later

### 2. **Read the file contents**
```python
# Use `.read()` to read the imported file and store it in a variable named `ip_addresses`

ip_addresses = file.read()
```
It then reads the file and stores the contents in a variable called `ip_addresses` as a string

### 3. **Convert the string into a list**
```python
# Use `.split()` to convert `ip_addresses` from a string to a list

ip_addresses = ip_addresses.split()
```
We then use `.split()` to convert the string into a list

### 4. **Iterate through the remove list**
```python
for element in ip_addresses:

  # Build conditional statement
  # If current element is in `remove_list`,
```
We then create a `for` loop to iterate through the remove list

### 5. **Remove IP addresses that are on the remove list**
```python
if element in remove_list:

  # then current element should be removed from `ip_addresses`

  ip_addresses.remove(element)
```
A conditional statement in the `for` loop will remove the ip address if it matches the remove list.

### 6. **Update the file with the revised list of IP addresses**
```python
# Convert `ip_addresses` back to a string so that it can be written into the text file

ip_addresses = " ".join(ip_addresses)

# Build `with` statement to rewrite the original file

with open(import_file, "w") as file:

  # Rewrite the file, replacing its contents with `ip_addresses`

  file.write(ip_addresses)
```
We then convert the list back to a string and then write it to the file.

---

## Summary

This algorithm can be useful to quickly update files automatically without having to manually go through and change each value, which can be time consuming and may be error prone.
