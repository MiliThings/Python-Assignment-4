# Task 1:

- We have created a list and named it sales.
- Then we opened a file using 'open' and saved it in a variable named 'file'
- we have named the file as 'sales_data.txt' and opened it in 'w' mode. So i am only allowed to write in the file nothing else.
- we ran a for loop to save the contents of the list in the file, each in new line.
- Then we manually closed the file using the close() function.
- Then we reopen the file in 'r' mode, just to read it and print the contents of the list.
- I cannot perform any other actions on it, except reading it.
- But this time we have opened the file using the 'with open' command which automatically closes the file so we dont have to manually close the file.
- Then we printed the file.
- On the next ste, we have reopened the file with 'w+' mode, which allows us to write in the file and then read it.
- We reopened the file , we have used ','.join(...) so convert the list into a comma separated string instead of line by line.
- Since we have written it over the old file, the previous content has been overwritten and the previous data as been deleted. 
- The file automatically closes because we have opened the file using 'with'


# Task 2

- We opened sales_data.txt again in 'r' mode using with open, so it closes on its own once we're done.
- First, we used .read() to get the whole file in one go as a single string, and printed it out.
- Next, we reopened the file and used .readline(), which only reads one line at a time starting from the top. We used .strip() on it to remove the \n at the end so it prints cleanly.
- Then we reopened the file one more time and used .readlines(), which reads every line and gives us back a list of strings, but each string still has its \n attached.
- We ran a list comprehension, [int(line.strip()) for line in lines], to strip the newline off every line and convert each one from a string into an integer, all in one step.
- We printed the final list to confirm we got back a list of integers matching the original sales list.
- Every file here was opened with 'with open', so we never had to manually close anything.


# Task 3: Append New Sales
- We created a new list called 'new_sales' holding the three new values, 5000, 2500, 1700.
- We opened sales_data.txt again, but this time in 'a' mode, which stands for append. Unlike 'w' mode, append mode does not erase what's already in the file — it just adds new content to the end.
- We ran a for loop and wrote each new sale on its own line, the same way we did in Task 1, converting each number to a string and adding "\n" after it.
- We reopened the file in 'r' mode and used .read() to print the whole file, so we can confirm the old sales are still there and the new ones got added after them.
- For the extra part, we reopened the file once more and used .readlines() to get a list where every line is one element, then used len() on that list to count how many lines the file has in total.
- Every file was opened using with open, so nothing had to be closed manually.


# Task 4: Generate summary report from file
- We opened sales_data.txt in 'r' mode using with open, then used .readlines() to grab every line as a list of strings, the same way we did in Task 2.
- We used a list comprehension, [int(line.strip()) for line in lines], to clean the newline off each line and convert every value into an integer, giving us sales_ints, a clean list of numbers.
- We used Python's built-in sum() function on sales_ints to get the total of all sales.
- We used max() and min() on the same list to get the highest and lowest sale values without writing any manual comparison loops.
- We calculated the average ourselves by dividing total_sales by len(sales_ints), which gives us the count of how many sales there are.
- We printed all four values, Total, Highest, Lowest, and Average, so the summary report is visible in one place.


# Task 5: Create product into file (user input)

- We opened a new file called products.txt in 'w' mode, so we start fresh with a new empty file.
- We ran a for loop 3 times, once for each product, and used input() to ask the user for the product's name and price.
- Inside the loop, we used file.write(name + " | " + price + "\n") to write each product on its own line in the exact ProductName | Price format the task asked for, joining the two values with a pipe character and spaces on either side of it.
- Once the loop finished and the with block closed the file for us, we reopened products.txt in 'r' mode to read it back.
- We used .readlines() to get every line as a list, then looped through that list and printed each line using .strip(), so we don't get an extra blank line from the leftover \n at the end of each entry.
- All file operations used with open, so there was no need to manually close anything, and since the file was reopened in 'w' mode at the start, running the script again cleanly overwrites any previous product entries instead of appending to them.


# Task 6: Read files safely (Error handling inside the file handling only)

- We imported the os module only for os.path.exists().
- We used input() to ask the user to type in a filename they want to open.
- We used os.path.exists(filename) inside an if condition to check whether a file with that name actually exists in the current folder, before we try to do anything with it.
- If the condition is True, we opened the file safely using with open in 'r' mode and printed its contents with .read().
- If the condition is False, meaning the file doesn't exist, we go to the else block and print "File not found. Please check the filename." instead of letting the program crash.
- This way, the whole safety check happens through a simple if/else condition.

# Task 7: Mini project

- We created the prices dictionary exactly as given, with each product name as a key and its original price as the value.
- We used input() to ask the user for a discount percentage, and wrapped it in float() since discounts can include decimals like 12.5.
- We opened discount_report.txt in 'w' mode so we start with a clean file each time.
- We made an empty list called discounted_values before the loop, so we could keep track of every discounted price and use it later for the average.
- We looped through the dictionary using prices.items(), which gives us both the product name and its original price on each iteration.
- Inside the loop, we calculated discounted_price by subtracting the discount amount (original_price * (discount_percent / 100)) from the original price.
- We appended each discounted_price to our discounted_values list so we could use it after the loop finishes.
- We wrote each line into the file using an f-string in the exact Product | Original Price | Discounted Price format the task asked for.
- For the extra part, after the loop we calculated total_items using len(prices) and average_discounted_price by dividing the sum of discounted_values by total_items.
- We wrote both of these as a summary at the bottom of the same file, still inside the same with block so everything goes into one file in one go.
- Finally, we reopened discount_report.txt in 'r' mode and used .read() to print the whole file, including the summary, to the terminal.


# How to Run the file
- For the basics, we need Python3, anything above python 3.6
- will need to install the jupyter notebook and save the file using .ipynb 
- or just use, shift enter to run the file
- or you can also run the file in the cmd by running the file as python3 filename.py and enter
