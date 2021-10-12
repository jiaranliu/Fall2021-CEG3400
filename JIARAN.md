
## Homework : CEG 3400

### Vulnerability Taxonomy CWE Homework

#### Name: Jiaran Liu

* CWE-200: Exposure of Sensitive Information to an Unauthorized Actor

```
   Exposure of sensitive information to an unauthorized actor is the product discloses 
sensitive information to participants who are not expressly authorized to access the 
information. This will make the attackers easy to access the secret informations.
   I have one project that is relate to this. The project want me to create a discord 
bot that will respond to the certain commands. So I create this bot and used its 
token to link my linux py code. After I tested it's working. I wanted to push all 
the codes to my github to save the code. Then the discord sent me a message, it says 
my bot token has found in github(link) and it will automatically generate a new one. 
So the problem is when I push the work it will generate a new token and all the code 
that rely on the token won't work properly.
   I fixed it by put the codes in .gitingore file to escape the discord detection. 
So that I can push the .gitingore file to save all the changes to the code without 
get trouble with the token.
```
