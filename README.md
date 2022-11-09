# Server managment course
Hello this is the documentation for the server managment course by Tero Karvinen.
# H1 Homework

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

Then I just restarted the services with commands "sudo systemctl restart salt-master.service" and "sudo systemctl restart salt-master.service" then just accepted the key

## Fourth assignment (c) 

The task for this was to run a state without the master-slave architecture and to analyze the debug print but I'm not quite sure to where to start with this.
