# Server managment course
Hello this is the documentation for the server managment course by Tero Karvinen.

# H1 Homework
[(src)](https://terokarvinen.com/2022/palvelinten-hallinta-2022p2/)

## First Assignment (x)

So for the first assingment we were to summarize the following articles: 

Karvinen 2020: ["Command Line Basics Revisited"](https://terokarvinen.com/2020/command-line-basics-revisited/)

- The article is basically a introduction to Linux command line.
- It Has some incredibly useful commands to navigate and do some basic stuff like add directories or files etc.
- The article also explains some of the more important directories that are located in the root of Linux.
- It also shows package managment like installing software.
    
Karvinen 2018: [Salt States – I Want My Computers Like This](https://terokarvinen.com/2018/salt-states-i-want-my-computers-like-this/)

- This article is about showing how to control agents with Salt
- For this article you need to have a already working master-servant [setup](https://terokarvinen.com/2018/salt-quickstart-salt-stack-master-and-slave-on-ubuntu-linux/)

Karvinen 2006: [Raportin kirjoittaminen](https://terokarvinen.com/2006/raportin-kirjoittaminen-4/?fromSearch=raportin%20kirjoittaminen)

- This article is about how to write a good report mostly focusing on the theme of the courses by Tero Karvinen
- The article is in Finnish so if you are interested in the article you can always use the browsers webpage translating option
- The articles explains different steps very well in my opinion as it explains the "goods and bads" and the "dos and not to dos" really well.

## Second Assignment (a)

For this assignment we were to make a file with Salt in 1 command. To accomplish this I used a command

  sudo salt-call --local state.single file.managed /tmp/firstfile
  
and it created a file since there was no such file in /tmp/ directory

![image](https://user-images.githubusercontent.com/77589513/199388847-b95d8734-3cb7-43eb-997a-04a5492ca9ac.png)

## Third Assignment (b)

This assignment was to make a idempotent to do this I first had to make a folder in /srv/ called "salt", in salt I created a new folder called test and finally into test I created a file called the "init.sls" which is used to create the idempotent. Then put all of this into the init.sls file:

![image](https://user-images.githubusercontent.com/77589513/199412946-8c49fe69-7f50-4e97-905a-2f8739dc5124.png)

It seems at this point I realized that something was wrong, I was unable make anything work properly and it seems the reason was that my master-servant setup did not work and I was unable to make it work even though I was reading this [guide](https://terokarvinen.com/2018/salt-quickstart-salt-stack-master-and-slave-on-ubuntu-linux/)

## Third assignment (c)

For this assignment I was told to collect information using salt and this was somethin possible as I could do it even without the master-servant setup as all I had to do was run a command:

  sudo salt-call --local grains.items osfinger
  
and I received a ton of information related to my machine as shown in this picture:

![image](https://user-images.githubusercontent.com/77589513/199424384-3c87e50c-e658-4101-94e3-5a8af90d6972.png)

![image](https://user-images.githubusercontent.com/77589513/199424180-63ea6bc0-9d81-4889-9345-bece68fe37c2.png)

![image](https://user-images.githubusercontent.com/77589513/199424197-0cce2f43-9063-4a21-81dd-0b114886dcb6.png)

## Final Assignment 

For this homework was about using something else besdes file.managed state which was a bit too hard for me so maybe next lecture there is a chance of learning more

(note. all of the commands and knowledge I used here were mostly gotten from the lecture as I saved screenshots from it unless mentioned otherwise). 

# H2 Package-File Service homework
[(src)](https://terokarvinen.com/2022/palvelinten-hallinta-2022p2/)

## First assignment (x)

For this assignment we were told to give a short summary from an article: https://terokarvinen.com/2018/salt-quickstart-salt-stack-master-and-slave-on-ubuntu-linux/ and the chapters "Understanding SaltStack", "SaltStack Fundamentals" and "SaltStack Configuration Managment Functions" from [Salt official documentation](https://docs.saltproject.io/en/getstarted/)

### Karvinen 2018: Salt Quickstart - Salt Stack Master and Slave on Ubuntu Linux

- The article is a quick guide to how to install a master and a slave machine.
- It also shows how to connect the master and slave machines.
- The article also shows some commands you can use on your slave machine.

### Understanding SaltStack

- All salt slaves receive commands simultaneously
- Every slave you have can be set to do their own thing and to call that specific slave you can use the set properties and arguments to specify which slave to use.
- Salt can be used to manage thousands of slaves at the same time.
- You can also automate most of the functions on Salt

### SaltStack Fundamentals 

- This chapter goes on how to install demo machines to test saltstack
- It also shows how to install saltstack also how to test, but as the chapter said it used the demo that you previously used it already had salt installed and I hoped regardless of that they would've showed the commands how to install it
- Also shows how to setup the master-minion connection and how to test it.
- It shows how to create salt states and target or apply states

### SaltStack Configuration Managment Functions

- On this chapter I learnt how to Call Salt state functions
- Understand the difference between Salt state and Salt execution functions
- Create the pillar Top.sls file 
- Define and assign some pillar keys to your systems
- Understand the default execution order
- Use requisites to declare execution order
- The chapter also has a lot of stuff that definetly goes over my head which I will read later to understand it better.

## Second assignment (a)

This assignment we were tasked to install, configure and test a daemon with package-file-service structure. Unfortunately this day I overslept for the lecture so I missed most of the crucial information so honestly I am completely unaware where I was supposed to go with this assignment.

## Third assignment (b)

This assignment we were tasked with installing a master and slave in 1 machine and suggested using a fresh virtual machine and that is what I did so I started with creating a new debian virtual machine. I ran the usual commands "sudo apt-get upgrade", "sudo apt-get update", "sudo apt-get install micro" as I do every time I start a new virtual machine. So to install them on the same machine I simply installed both master and slave with commands "sudo apt-get install -y salt-master" and "sudo apt-get install -y salt-minion next I added the machine as master and a id with command sudoedit /etc/salt/minion 

![image](https://user-images.githubusercontent.com/77589513/200889921-2725d285-1cad-4f09-95e6-1310f3b45b02.png)

![image](https://user-images.githubusercontent.com/77589513/200890050-a2880855-2811-48ac-93f2-5f3128353846.png)

Then I just restarted the services with commands "sudo systemctl restart salt-master.service" and "sudo systemctl restart salt-minion.service" then just accepted the key

## Fourth assignment (c) 

The task for this was to run a state without the master-slave architecture and to analyze the debug print but I'm not quite sure to where to start with this.

# H3 Git
[(src)](https://terokarvinen.com/2022/palvelinten-hallinta-2022p2/)

## First Assignment (a)

For this assignment was to write this Raport in MarkDown, but as I did that from the start so I have already done so.

## Second Assignment (b)

For this assignment we were tasked with creating a offline git directory an in the directory it had to include the word "cat" in the name so I created a new directory called the catdirectory and in there I initalized git with the command

> git init

next I created 2 files so it would not be empty called "cat.txt" and "cat.md" I wrote some random text in there and then used the command:

> git add .

which basically makes git notice you want to make updates to the git directory and lastly:

> git commit -m "Commit information"

I happened to add the files and commit the files on separate commits but that git commit -m "Info" commits the changes in the directory to git.

## Third Assignment (c)

For this assignment we were tasked with testing the "git reset --hard" by making a stupid mistake to git and NOT commiting it but still it's in there and want to get rid of it. I simply ran the command after making a random text file and nothing special happened except after looking at the directory the file disappeared.

## Fourth Assignment (d)

For this assignment we were tasked with creating a new depository to GitHub and the depository has to include the word car in the name and in the description of the depository and adding files to it. So I begin by going to https://github.com/ as I already am logged in it looks like this:

![image](https://user-images.githubusercontent.com/77589513/202265600-c37ec7aa-0ff0-4c06-9029-151b82702be4.png)

and choose the "New" option from top left corner as it opens up a setup like [this](https://i.imgur.com/HFBLuJE.png) which gives options to add a README and license files instead of the "Create a new repository" which simply creates a clean repository without anything in there. and make sure it is public as it is a school project and I want it to be seen publically and this is how the repository looks like:

![image](https://user-images.githubusercontent.com/77589513/202268555-b0429524-805d-4d4e-9069-be9558f79500.png)

## Fifth Assignment (e)

For this assignment we were given to Clone the previously made repository, change things up a little bit and to push it to a web server. I tried looking up for something related to it but I got incredibly confused from all of it so I was unable to do this

# H4 Omat komennot
[(src)](https://terokarvinen.com/2022/palvelinten-hallinta-2022p2/)

## First assignment (a)

For this assignment we were tasked with just creating a script that runs as a command on your machine and install it on a slave machine with Salt. To start this I recalled how we did this on the lecture so I started by creating a file called "heimaailma.sh" with the command micor heimaailma.sh then added these lines into the file:

![image](https://user-images.githubusercontent.com/77589513/203577577-672c58a7-df79-467d-a88b-76ba5696485b.png)

The first line makes it so it uses bash as the default shell for executing the commands and then just added the line echo "hei maailma" which just prints the string hei maailma on the terminal.
sources: (https://www.baeldung.com/linux/bash-shebang-lines)
Next up from my recollection all I had to do was copy the heimaailma.sh file to /usr/local/bin/ folder with the command 

    sudo cp heimaailma.sh /usr/local/bin/
    
then just tried running the command like normal, but for some reason it did not run and I was quite not sure what was the issue here so I decide to google what was wrong and the issue was simple after reading this [article](https://www.baeldung.com/linux/bash-shebang-lines) I realized I forgot 1 step that made it not work, I forgot to grant permissions to the file so it can read and write anywhere in the system and to give the permissions I used command:

    chmod ugo+x heimaailma.sh
    
After running this command I tested the command by just running "heimaailma.sh" and it worked also tested by going to different directories just to make sure and it did indeed work. Finally I set it up so it would install the command to slaves. First what I did was go to directory /srv/salt/ if there is no salt then just create one. Next I created a folder that I named heimaailma. Next I created a init.sls file and added this:

![image](https://user-images.githubusercontent.com/77589513/203627306-96d8a80f-f396-4189-8d27-f7975693b64a.png)

The first line is the absolute path of the command where it is located, next line is "file.managed" which means you are managing the files when this is ran, next is the source basically the same file of the command except it has to be located in the salt folder and mode gives the command proper permissions. Finally I tested if it worked with the command "sudo salt-call --local state.apply heimaailma as you can see below it worked.

![image](https://user-images.githubusercontent.com/77589513/203628904-52e04afa-7374-4675-9e6a-8ff070012e0d.png)

Here is also the image of running the command: "ls -l /usr/local/bin/"

![image](https://user-images.githubusercontent.com/77589513/203634405-73f85d93-44f9-4797-83c3-18e603f85992.png)


## Second Assignment (b)

For this assignment I was given the task of doing a whatsup.sh shell script ant turning it into a command. This whatsup.sh is supposed to be indicative of something like showing the time etc. and sending it to slaves just like before. So basically for this one I did everything exactly the same besides for the names of the files and what was inside the script. 

Script:

![image](https://user-images.githubusercontent.com/77589513/203633805-f45e386a-ffe4-4ac8-8eb2-17825b775e9b.png)

init.sls:

![image](https://user-images.githubusercontent.com/77589513/203633852-01581483-9aa9-4352-9738-aad320c4fa4a.png)

Working example:

![image](https://user-images.githubusercontent.com/77589513/203634857-5ad6d22a-3ded-49bb-b977-ee44013a5896.png)

Salt test:

![image](https://user-images.githubusercontent.com/77589513/203635225-3aeacaad-d9e9-41b9-8f32-71214c26f767.png)

## Third Assignment (c)

For this assignment we were tasked with creating a command using a python script with the name hello.py and to install it on a slave just like previous tasks. So I start with creating a directory in the home directory called hello, then created a file called hello.py added the line print("Hello World!") to test it works I ran command "python3 hello.py" it was a success it printed "Hello World!" as excpected. So next I moved to begin making it into a command by adding the Shebang above the print line called: #!/usr/bin/python3 quickly added the permissions with the command "sudo chmod ugo+x hello.py" then copied the file to /usr/local/bin/ then continued to /srv/salt/ and created a directory called hello and created init.sls file into the hello folder and into the init.sls file I put lines:

![image](https://user-images.githubusercontent.com/77589513/203641301-c7cfd07c-4b7b-4ae1-a70a-7aef73c2c0ec.png)

and sent it to the slave:

![image](https://user-images.githubusercontent.com/77589513/203641879-8e22a2e5-0189-4879-b9c5-82d9a401f38a.png)

Could not finish the entire homework as I did not have enough time but I will be finishing these on my own time later.
