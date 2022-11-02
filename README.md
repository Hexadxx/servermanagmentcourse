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

