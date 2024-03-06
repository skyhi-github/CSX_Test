![image](https://github.com/skyhi-github/CSX_Test/assets/64489355/0fb46c2b-0aed-417b-954a-17c9f89ad318)

## *[Testing in Cambodia Securities Exchange's Software Developer Job](http://csx.com.kh/about/opportunities/viewPost.do)*

**1 Find index of array** 
    
```Python
numbers = [10, 20, 30, 40, 50]

# Find the index of the element 30
index_30 = numbers.index(30)
print("Index of 30:", index_30)  # Output: 2

# Find the index of the element 50
index_50 = numbers.index(50)
print("Index of 50:", index_50)  # Output: 4
```

**2 Find unique in character** 
    
```Python
def find_unique_characters(input_string):
# Use a set to store unique characters
unique_chars = set()

# Iterate through each character in the input string
for char in input_string:
    # Add the character to the set
    unique_chars.add(char)

# Convert the set back to a string
unique_string = ''.join(unique_chars)

    return unique_string

# Example usage
input_string = "hello world"
unique_characters = find_unique_characters(input_string)
print("Unique characters:", unique_characters)  # Output: "helo wrd"
```
 **3 Sort Value**
```Python
numbers = [5, 2, 8, 1, 4]

# Sort numbers in ascending order
numbers.sort()
print("Sorted numbers in ascending order:", numbers)  # Output: [1, 2, 4, 5, 8]

# Sort numbers in descending order
numbers.sort(reverse=True)
print("Sorted numbers in descending order:", numbers)  # Output: [8, 5, 4, 2, 1]
```
 **4 Dynamic SQL**
```sql
-- Option 1: Concatenating SQL strings directly
DECLARE @sqlQuery1 NVARCHAR(MAX)
SET @sqlQuery1 = 'SELECT * FROM users WHERE 1 = 1'
IF @name IS NOT NULL
    SET @sqlQuery1 = @sqlQuery1 + ' AND name = ''' + @name + ''''
IF @age IS NOT NULL
    SET @sqlQuery1 = @sqlQuery1 + ' AND age = ' + CAST(@age AS NVARCHAR(10))
EXEC sp_executesql @sqlQuery1

-- Option 2: Using parameterized queries
DECLARE @sqlQuery2 NVARCHAR(MAX)
SET @sqlQuery2 = 'SELECT * FROM users WHERE 1 = 1'
IF @name IS NOT NULL
    SET @sqlQuery2 = @sqlQuery2 + ' AND name = @name'
IF @age IS NOT NULL
    SET @sqlQuery2 = @sqlQuery2 + ' AND age = @age'
EXEC sp_executesql @sqlQuery2, N'@name NVARCHAR(50), @age INT', @name, @age

-- Option 3: Using CONCAT function
DECLARE @sqlQuery3 NVARCHAR(MAX)
SET @sqlQuery3 = CONCAT('SELECT * FROM users WHERE 1 = 1',
                        CASE WHEN @name IS NOT NULL THEN CONCAT(' AND name = ''', @name, '''') ELSE '' END,
                        CASE WHEN @age IS NOT NULL THEN CONCAT(' AND age = ', CAST(@age AS NVARCHAR(10))) ELSE '' END)
EXEC sp_executesql @sqlQuery3

-- Option 4: Using COALESCE function
DECLARE @sqlQuery4 NVARCHAR(MAX)
SET @sqlQuery4 = 'SELECT * FROM users WHERE 1 = 1'
SET @sqlQuery4 = @sqlQuery4 + COALESCE(' AND name = ''' + @name + '''', '')
SET @sqlQuery4 = @sqlQuery4 + COALESCE(' AND age = ' + CAST(@age AS NVARCHAR(10)), '')
EXEC sp_executesql @sqlQuery4

-- Option 5: Using QUOTENAME function
DECLARE @sqlQuery5 NVARCHAR(MAX)
SET @sqlQuery5 = 'SELECT * FROM users WHERE 1 = 1'
SET @sqlQuery5 = @sqlQuery5 + CASE WHEN @name IS NOT NULL THEN ' AND name = ' + QUOTENAME(@name, '''') ELSE '' END
SET @sqlQuery5 = @sqlQuery5 + CASE WHEN @age IS NOT NULL THEN ' AND age = ' + CAST(@age AS NVARCHAR(10)) ELSE '' END
EXEC sp_executesql @sqlQuery5
```
**5 Stock Buy and Sell Problem**
```python
def max_profit(prices):
    if not prices:
        return 0
    
    buy_price = prices[0]  # Initialize the buy price
    max_profit = 0  # Initialize the maximum profit
    
    max_profit_days = []  # List to store buy and sell days with maximum profit
    
    for i in range(1, len(prices)):
        if prices[i] < buy_price:  # If the current price is less than the buy price, update the buy price
            buy_price = prices[i]
        else:  # If the current price is greater than or equal to the buy price, calculate the profit
            profit = prices[i] - buy_price
            if profit > max_profit:  # If the profit is greater than the maximum profit, update the maximum profit and buy/sell days
                max_profit = profit
                max_profit_days = [(prices.index(buy_price), i)]
            elif profit == max_profit:  # If the profit is equal to the maximum profit, append the buy/sell days to the list
                max_profit_days.append((prices.index(buy_price), i))
    
    return sum(max_profit), max_profit_days

# Test the function with the given example
prices = [7, 1, 5, 4, 6, 4]
max_profit, max_profit_days = max_profit(prices)
print("Maximum Profit:", max_profit)
print("Buy and Sell Days with Maximum Profit:", max_profit_days)
```
**6 Calculate Possible Increment**
```python
def calculate_possible_increments(price_range, increment):
    # Extract the start and end prices from the price range
    start_price, end_price = price_range
    
    # Check if the user input is within the specified range
    if increment < 0 or increment > (end_price - start_price):
        return "Error: Increment is out of range"
    
    # Initialize a variable to count the number of possible increments
    possible_increments = 0
    
    # Iterate through the price range and count the possible increments
    for price in range(start_price, end_price + 1, increment):
        possible_increments += 1
    
    return possible_increments
    
# Test the function for different price ranges and increments
price_range = (0, 4000)
increment = 10
print("Price range:", price_range)
print("Increment:", increment)
print("Number of possible increments:", calculate_possible_increments(price_range, increment))

price_range = (4000, 20000)
increment = 20
print("\nPrice range:", price_range)
print("Increment:", increment)
print("Number of possible increments:", calculate_possible_increments(price_range, increment))

price_range = (20000, 40000)
increment = 50
print("\nPrice range:", price_range)
print("Increment:", increment)
print("Number of possible increments:", calculate_possible_increments(price_range, increment))

# Test for out of range input
increment = 100
print("\nPrice range:", price_range)
print("Increment:", increment)
print("Number of possible increments:", calculate_possible_increments(price_range, increment)))
```
**7 Tree Traversal Technique**
![image](https://github.com/skyhi-github/CSX_Test/assets/64489355/3d1389c1-11f4-4ef0-94af-fdfbd4504e67)
```python
class TreeNode:
    def __init__(self, val=0, left=None, right=None):
        self.val = val
        self.left = left
        self.right = right

def build_tree(preorder, inorder):
    if not preorder or not inorder:
        return None
    
    root_val = preorder[0]
    root = TreeNode(root_val)
    
    # Find the index of root in inorder traversal
    root_index = inorder.index(root_val)
    
    # Recursively build left and right subtrees
    root.left = build_tree(preorder[1:1+root_index], inorder[:root_index])
    root.right = build_tree(preorder[1+root_index:], inorder[root_index+1:])
    
    return root

def pre_order_traversal(root):
    if root:
        print(root.val, end=" ")
        pre_order_traversal(root.left)
        pre_order_traversal(root.right)

def in_order_traversal(root):
    if root:
        in_order_traversal(root.left)
        print(root.val, end=" ")
        in_order_traversal(root.right)

# Example usage
preorder = [3,9,20,15,7]
inorder = [9,3,15,20,7]

root = build_tree(preorder, inorder)

print("Pre-order traversal:")
pre_order_traversal(root)

print("\nIn-order traversal:")
in_order_traversal(root)
```
