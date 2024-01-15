# Update-a-File-Through-a-Python-Algorithm

<h2>Introduction</h2>

An important part of cybersecurity is controlling access to restricted content. In this lab, I'll work with a text file containing IP addresses that are allowed to access specific restricted content at my organization.

Parsing a file allows security analysts to read and update the contents. Python helps analysts develop algorithms to automate the process of parsing files and keeping them up-to-date.

I'll develop an algorithm that parses this text file of IP addresses and updates the file by removing the addresses that no longer have access to the restricted content.

<h2>Scenario</h2>

I am a security professional working at a healthcare company. As part of my job, I'm required to regularly update a file that identifies the employees who can access restricted content. The contents of the file are based on who is working with personal patient records. Employees are restricted access based on their IP address. There is an allow list of IP addresses permitted to sign into the restricted subnetwork. There's also a remove list that identifies which employees I must remove from this allow list.
My task is to create an algorithm that uses Python code to check whether the allow list contains any IP addresses identified on the remove list. If so, I should remove those IP addresses from the file containing the allow list.

<h2>Task 1</h2>

My eventual goal is to develop an algorithm that parses a series of IP addresses that can access restricted information and removes the addresses that are no longer allowed. Python can automate this process.

I'm given a text file called ```"allow_list.txt"``` that contains a series of IP addresses that are allowed to access restricted information.

There are IP addresses that should no longer have access to this information, and their IP addresses need to be removed from the text file. I'm given a variable named ```remove_list``` that contains the list of IP addresses to be removed.

Display both variables to explore their contents, and run the cell.

![image](https://github.com/n8som/Create-Another-Algorithm/assets/110139109/d78f2ecd-b453-4bc8-bdff-bf078c2a947c)

The first line of the output shows the name of the text file. The second line of the output shows the list of IP addresses from the remove_list.

<h2>Task 2</h2>

In this task, start by opening the text file using the ```import_file``` variable, the ```with``` keyword, and the ```open()``` function with the ```"r"``` parameter. 

For now, I'll write the first line of the ```with``` statement. Running this code will produce an error because it will only contain the first line of the ```with``` statement; I'll complete this ```with``` statement in the task after this.

![image](https://github.com/n8som/Create-Another-Algorithm/assets/110139109/6df508d2-1041-4ad2-b270-f6942c649fc9)

<h2>Task 3</h2>

Now, use the ```.read()``` method to read the imported file and store it in a variable named ```ip_addresses```.

Afterward, display ```ip_addresses``` to examine the data in its current format.

![image](https://github.com/n8som/Create-Another-Algorithm/assets/110139109/a6ba10f1-7ac5-4855-8706-f3579642dc69)

Four IP addresses in the allow list are also in the remove_list.

<h2>Task 4</h2>

After reading the file, reassign the ```ip_addresses``` variable so its data type is updated from a string to a list. Use the ```.split()``` method to achieve this. Adding this step will allow me to iterate through each of the IP addresses in the allow list instead of navigating a large string that contains all the addresses merged.

Afterward, display the ```ip_addresses``` variable to verify that the update took place.

![image](https://github.com/n8som/Create-Another-Algorithm/assets/110139109/a05da264-f87f-4209-8aa1-4dbbf4ec4e96)

<h2>Task 5</h2>

Now, I'll write code that removes the elements of ```remove_list``` from the ```ip_addresses``` list. This will require both an iterative statement and a conditional statement.

First, build the iterative statement. Name the loop variable ```element```, loop through ```ip_addresses```, and display each element. 

![image](https://github.com/n8som/Create-Another-Algorithm/assets/110139109/2c4df99f-6ed1-4859-8825-650f393d9172)

<h2>Task 6</h2>

Now, build a conditional statement to remove the elements of ```remove_list``` from the ```ip_addresses``` list. The conditional statement should be placed inside the iterative statement that loops through ```ip_addresses```. In every iteration, if the current element in the ```ip_addresses``` list is in the ```remove_list```, the ```remove()``` method should be used to remove that element.

Afterward, display the updated ```ip_addresses``` list to verify that the elements of remove_list are no longer in the ```ip_addresses```. 

![image](https://github.com/n8som/Create-Another-Algorithm/assets/110139109/08f0e2c6-5b2c-44dc-b958-035904fccac7)

<h2>Task 7</h2>

The next step is to update the original file that was used to create the ```ip_addresses``` list. A line of code containing the ```.join()``` method has been added to the code so that the file can be updated. This is necessary because ```ip_addresses``` must be in string format when used inside the with statement to rewrite the file.

The ```.join()``` method takes in an iterable (such as a list) and concatenates every element of it into a string. The ```.join()``` method is applied to a string consisting of the character that will be used to separate every element in the iterable once it's converted into a string. In the code below, the method is applied to the string ```" "```, which contains just a space character. The argument of the ```.join()``` method is the iterable I want to convert, and in this case, that's ```ip_addresses```. As a result, it converts ip_addresses from a list back into a string with a space between each element and the next.

After this line with the ```.join()``` method, build the ```with``` statement that rewrites the original file. Use the ```"w"``` parameter when calling the ```open()``` function to delete the contents in the original file and replace it with what I want to write.

This code cell will not produce an output.

![image](https://github.com/n8som/Create-Another-Algorithm/assets/110139109/55669049-c121-478a-9957-319ab4794cae)

<h2>Task 8</h2>

In this task, I'll verify that the original file was rewritten using the correct list.

Write another ```with``` statement, this time to read in the updated file. Start by opening the file. Then read the file and store its contents in the ```text``` variable.

Afterward, display the ```text``` variable to examine the result.

![image](https://github.com/n8som/Create-Another-Algorithm/assets/110139109/75ec5d87-9b74-45e0-9009-9ef112ff46d0)

<h2>Task 9</h2>

The next step is to bring all of the code I've written leading up to this point and put it all into one function.

Define a function named ```update_file()``` that takes in two parameters. The first parameter is the name of the text file that contains IP addresses (call this parameter import_file). The second parameter is a list that contains IP addresses to be removed (call this parameter remove_list).

Note that this code cell will not produce an output.

![image](https://github.com/n8som/Create-Another-Algorithm/assets/110139109/94120daa-8e6c-4771-adaa-f7a4ea2d481a)

The benefits of incorporating the algorithm into a single function help organize the code and make it reusable. If you want to execute the algorithm more than once, all you have to do is call the function that contains it.

<h2>Task 10</h2>

Finally, call the ```update_file()``` that I defined. Apply the function to ```"allow_list.txt"``` and pass in a list of IP addresses as the second argument.

Use the following list of IP addresses as the second argument:

```["192.168.25.60", "192.168.140.81", "192.168.203.198"]```

After the function call, use a ```with``` statement to read the contents of the allow list. Then display the contents of the allow list. Run it to verify that the file has been updated by the function.

![image](https://github.com/n8som/Create-Another-Algorithm/assets/110139109/cced42bb-b55b-474c-897d-28637811b99c)

<h2>Conclusion</h2>

What are the key takeaways from this lab?

- Python has functions and syntax that help me import and parse text files.
  - The ```with``` statement allows me to efficiently handle files.
  - The ```open()``` function allows me to import or open a file. It takes in the name of the file as the first parameter and a string that indicates the purpose of opening the file as the second parameter.
    - Specify ```"r"``` as the second parameter if I'm opening the file for reading purposes.
    - Specify ```"w"``` as the second parameter if I'm opening the file for writing purposes.
  - The ```.read()``` method allows me to read in a file.
  - The ```.write()``` method allows me to append or write to a file.
- I can use a ```for``` loop to iterate over a list.
- I can use an ```if``` statement to check if a given value is in a list and execute a specific action if so.
- I can use the ```.split()``` method to convert a string to a list.
- I can use Python to compare the contents of a text file against elements of a list.
- Algorithms can be incorporated into functions. When defining a function, I must specify the parameters it takes in and the actions it should execute.
