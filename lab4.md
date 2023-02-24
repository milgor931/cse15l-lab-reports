# Lab Report 4

* Competition tutorial to learn how to use commands faster *

1) ***Setup:** Delete any existing forks of the repository you have on your account*

If I had created a fork of the lab 4 repository before, I went to the fork "settings" tab, scrolled all the way down, and clicked on "Delete this repository". I had to type the name of the repo to successfully delete it to get everything ready for the competition.

![image](https://user-images.githubusercontent.com/40010548/221020019-7d4243a1-82b9-459a-825d-41272cdc5384.png)

2) ***Setup:** Fork the repository*

I went to the lab 4 repo on github using this [link](https://github.com/ucsd-cse15l-w23/lab7) and clicked the "Fork" button to create a fork of the repository on my Github account. 

![image](https://user-images.githubusercontent.com/40010548/221019586-063fc723-83e5-4e61-ab73-22daff4c8386.png)

3) Next it to start the stopwatch on a phone or laptop!

![image](https://user-images.githubusercontent.com/40010548/221020207-2fdbf248-0f1d-43aa-b535-28e77096014f.png)

4) Log into ieng6

Since I had logged into ieng6 before and it was the last command I had run before accessing the remote server, I pressed `<up><enter>` to save time and log into the remote server super fast since I had already set up the ssh key. 

![image](https://user-images.githubusercontent.com/40010548/221012202-406807ff-6e9f-4fde-ba72-51984334d233.png)

5) Clone your fork of the repository from your Github account

I first clicked on the "Code" button in my fork on Github and used the "Copy" button to copy the "SSH" key. This works because I had already configured the ssh key on github before starting this project to make the process of using git to add, commit, and push changes to my Github fork super easy. 

![image](https://user-images.githubusercontent.com/40010548/221021162-e0f27ae2-24e8-47dc-9835-8286d191dab3.png)

Since I am already connected to the remote server, I was able to write git clone and `<Right-Click>` to easily paste the SSH key I had copied from Github to create the repository. 

![image](https://user-images.githubusercontent.com/40010548/221021707-5dd31836-8f46-4958-8471-342807528519.png)

I then change directory into the newly cloned lab7. I type `cd la` and press `<Tab>` and it autocompletes to `lab7/` to help me save time on typing.

![image](https://user-images.githubusercontent.com/40010548/221022438-5a143b1a-ab22-4c65-b5f3-ba5f4e1558f3.png)

6) Run the tests, demonstrating that they fail

Since I had already used the commands for compiling the tester and .java files before, I can just press `<up><up><up><up><up><enter>` to get the compiler code and  `<up><up><up><up><up><up><enter>` to actually run the JUnit tests more efficiently.

![image](https://user-images.githubusercontent.com/40010548/221023182-87f46bb8-1f62-468b-aa50-b5e8ad7b9696.png)

![image](https://user-images.githubusercontent.com/40010548/221023289-45fa9e78-f94d-482b-a4ef-e83f467dc979.png)

7) Edit the code file to fix the failing test

To fix the failing test, I can use the `nano` editor to see and edit the file. I typed `nano Li` and press `<Tab>` so that it autocompletes to `nano ListExamples.` and then I type `java` to complete the ending.

![image](https://user-images.githubusercontent.com/40010548/221041247-608fe916-5c9f-488e-a922-58bce6d0848c.png)

The nano editor opens and I can use the arrow keys to quickly skim through the code and find the line with the issue and edit it. In this case, the line to fix it to change `index1 += 1` in the last while loop to `index2 += 1`. To save and exit out, I press `<Ctrl-O>` to save, `<Enter>` to confirm the file name, and `<Ctrl-X` to exit. 

![image](https://user-images.githubusercontent.com/40010548/221041527-059d41db-347d-443c-85b0-fdd8dbba4ab2.png)

8) Run the tests, demonstrating that they now succeed

Once again, use the `<up>` key to re-compile and run the JUnit tests again. I press `<up><up><up><up><up><up><enter>` to get the compiler code and  `<up><up><up><up><up><up><up><up><enter>` to actually run the JUnit tests more efficiently.

![image](https://user-images.githubusercontent.com/40010548/221047805-98274974-9324-4cce-b0b9-9fb9cb32bd58.png)

9) Commit and push the resulting change to your Github account (you can pick any commit message!)

First, I wrote `git add Li` and pressed `<Tab>` to autocomplete to at the file to be staged as a commit. 

![image](https://user-images.githubusercontent.com/40010548/221048126-9671c7b5-6e3d-48e3-a99e-a210d255fbca.png)

I then wrote `git commit -m "update"` to actually commit the changes.

![image](https://user-images.githubusercontent.com/40010548/221048166-0b219726-0c0d-4a64-aaad-eb0b65fea81c.png)

Lastly, I wrote `git push` to actually push the changes to Github. 

![image](https://user-images.githubusercontent.com/40010548/221067758-cfeae4c7-6b8e-48ae-b395-d18bfcaefd4f.png)

And that's it! Time!

