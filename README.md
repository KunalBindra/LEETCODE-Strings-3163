# LEETCODE-Strings-3163
The code provided is a method in Java that takes a string, `word`, and compresses it by counting consecutive identical characters up to a maximum of 9. Let's step through how it works using a dry run.

### Code Explanation

1. `n = word.length()` retrieves the length of the input string `word`.
2. A `StringBuilder` object, `sb`, is initialized to build the result.
3. The main loop runs with two pointers, `i` and `j`, initialized to 0. `i` marks the start of a new character sequence, while `j` traverses to count identical characters.
4. For each sequence of identical characters:
   - `count` is incremented until a different character is encountered, or the count reaches 9.
   - The count and character are appended to `sb`.
5. Finally, `sb` is converted to a string and returned.

### Dry Run Example

Let's dry-run the method with an example input:

#### Example
**Input:** `"aaabbbbcccd"`

1. **Initial Variables:**  
   `n = 11`, `sb = ""`, `i = 0`, `j = 0`

2. **Loop Iterations:**

   - **First Sequence (`"aaa"`)**  
     - `i = 0`, `j = 0`, `count = 0`  
     - `word[0] == word[1] == word[2] == 'a'`  
     - `count` becomes 3, `j` moves to 3.  
     - Append `"3a"` to `sb`, so `sb = "3a"`.
     - Update `i = 3`.

   - **Second Sequence (`"bbbb"`)**  
     - `i = 3`, `j = 3`, `count = 0`  
     - `word[3] == word[4] == word[5] == word[6] == 'b'`  
     - `count` becomes 4, `j` moves to 7.  
     - Append `"4b"` to `sb`, so `sb = "3a4b"`.
     - Update `i = 7`.

   - **Third Sequence (`"ccc"`)**  
     - `i = 7`, `j = 7`, `count = 0`  
     - `word[7] == word[8] == word[9] == 'c'`  
     - `count` becomes 3, `j` moves to 10.  
     - Append `"3c"` to `sb`, so `sb = "3a4b3c"`.
     - Update `i = 10`.

   - **Fourth Sequence (`"d"`)**  
     - `i = 10`, `j = 10`, `count = 0`  
     - `word[10] == 'd'`  
     - `count` becomes 1, `j` moves to 11.  
     - Append `"1d"` to `sb`, so `sb = "3a4b3c1d"`.
     - Update `i = 11`.

3. **End:** `i == n`, so return `sb.toString()`.

**Output:** `"3a4b3c1d"`
