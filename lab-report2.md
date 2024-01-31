
# LabReport2

## Part1

```java
import java.io.IOException;
import java.net.URI;


 class Handler implements URLHandler{
    String result ="";
    
    

    public String handleRequest(URI url){
         String query = url.getQuery();
         if(url.getPath().equals("/add-message")){
            
            String[] param = query.split("&");
            
            if(param.length == 2 && param[0].startsWith("s=") && param[1].startsWith("user=")){
                String[] message = param[0].split("=");
                String[] users= param[1].split("=");
                result += String.format("%s: %s \n",users[1],message[1]);
                
                return result;
            }
         }

          return "No message yet!"; 
    }


}


class ChatServer {
    public static void main(String[] args) throws IOException{
        if(args.length == 0){
            System.out.println("Missing both port number and file path! Try any number between 1024 to 49151");
            return;
        }
        

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
```



* Firstly, let's start with the process of compiling. For starting the server, we need to `cd` our working directory to wavelet for accessing Server.java and ChatServer.java files, then we may compile both by using `javac` and put both as arguments. The reason we need Server.java is that it provides the method called `start` for us to start a server by putting port number and URLHandler as arguments. It helps us to create a website page with functions we created in ChatServer.java.
 
* For this ChatServer file, it imports `java.io` and `java.net` classes from standard library in java for handling Input/output(`IOException`) and dealing with URL(`URI`). Then we start our class class called Handler, which implements URLhandler interface for us to override HandRequest method in it. We starts wtih creating an String variable called `result`, which will be responsible to store all contents we input to the website. For overriding the HandRequest method, we put URL as an argument, which help us to investigate and modify the content of website. We created a String variable called query, by calling `.getQuery()` to store the query of the URL. Since we are trying to handle `/add-message` command, we check the Path of URLif it is `/add-message`. 

* If the result of `if` statement is true, we starts with creating a String variable called `param` by splitting the query with `&`, because we   expect the query in the format of `s=<string>&user=<string>`. This is also the reason why we need to check if the length of param is 2, `param[0]`
starts with `s=`, `param[1]` starts with `user=`. For fulfilling the format, we expect `param[0]` be `s=<string>` and `param[1]` be `user=<string>`, and only one `&` exists in the query. For getting the information we need, we create two String Array called `message` and  `users`. Since we expect our out put consists of `user: message`, by splitting both `param[0]` and `param[1]` with `=`, we can store the two    `<string>` we need for output into `users[]`and `message[]`. After that, for display the output in the way we want, we call the method of `String.format` for formatting it in `"%s: %s \n"`, we put `user[1]` as the first argument, since we would like to see the information of user before `:`, then we put `message[1]`as the second argument for putting the message information after `:`. For storing  informations, we use the `result` we created. If the Path of URL does not equal to `/add-message`, I give `"No message yet!"` information for without any input. For starting a website, we need have a `main` method for getting input from interminal, we throw IOException for avoiding invalid input. If there is no argument, we will give a message `"Missing both port number and file path! Try any number between 1024 to 49151"`. If the input is valid, we will create an int variable called port to store the number we got from input, and put it as an argument for `.start()`method calling from Server class, and `new Handler()` as the second argument for starting the Server.

* For the server number, I put ChatServer 6000 for the website.

  <img width="1408" alt="Screenshot 2024-01-30 at 9 51 06 AM" src="https://github.com/LC0229/cse15l-lab-reports/assets/156004283/e4d72ae8-2eae-4bc9-bf59-5f302e6a18a7">

  *We startswith the first example, by inputting `/add-message?s=Hello&user=jpolitz` as Path, it called the `handleRequest` method with `https://0-0-0- 0-6000-ru8ns4r41n8t7okit8dtdi7d7k.us.edusercontent.com/add-message?s=Hello&user=jpolitz` argument, it gives `s=Hello` and `user=jpolitz`, it gives 
  the information of user `jpolitz` and message `Hello`, we can see by putting these two `<string>` as arguments into `String.format`, the `result` will be print 
  out with the format we want with information we got.

  
  <img width="1408" alt="Screenshot 2024-01-30 at 9 52 36 AM" src="https://github.com/LC0229/cse15l-lab-reports/assets/156004283/96a17a96-d6fd-48d3-a290-2637485f7776">
  
  * By inputting `/add-message?s=Hi&user=Leon` as Path, it called the `handleRequest` method with `https://0-0-0-0-6000
  ru8ns4r41n8t7okit8dtdi7d7k.us.edusercontent.com/add-message?s=Hi&user=Leon` argument, it gives `s=Hello` and `user=jpolitz`, it gives 
  the information of user `Leon` and message `Hi`, we can see by putting these two `<string>`as arguments into `String.format` , the `result` 
   will be print out with the format we want with information we got.

 




## Part2

Private Key

```
chenshengrui@zuis-MacBook-Pro ~ % cd .ssh
chenshengrui@zuis-MacBook-Pro .ssh % ls
id_rsa          id_rsa.pub      known_hosts
chenshengrui@zuis-MacBook-Pro .ssh % pwd
/Users/chenshengrui/.ssh
```



By using `ls`, we can see `id_rsa` is in the `/.ssh` folder. By using `ls` I can see both my public key and private keystoring location on my local device. By using `pwd`, I can see the absolute path.



Public Key

```
[shc067@ieng6-203]:~:42$ cd .ssh
[shc067@ieng6-203]:.ssh:43$ ls
authorized_keys  id_rsa id_rsa.pub
[shc067@ieng6-203]:.ssh:44$ pwd
/home/linux/ieng6/oce/12/shc067/.ssh
```


By using `ls`, we can see the keys in the ieng6 file system. By using `pwd`, I can see the absolute path.



<img width="777" alt="Screenshot 2024-01-27 at 5 28 50 PM" src="https://github.com/LC0229/cse15l-lab-reports/assets/156004283/105465ae-6734-4b84-81a8-65d7bcf22b69">


A terminal interaction where you log into your ieng6 account without being asked for a password.





# Part3

From Lab2 to Lab3, I learned one of the most important skill is remote controlling by using terminal, it's not like zoom remote. It's more make me looks like a hacker:). The ways we learned to copy keys and files into remote servers are all really helpful. By starting servers, we can actually change the content of website is also the thing I've never seen. I believe this will be a great start for understanding and implementing our concepts
into real world!

