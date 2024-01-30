
<img width="784" alt="Screenshot 2024-01-27 at 5 33 54 PM" src="https://github.com/LC0229/cse15l-lab-reports/assets/156004283/219dd894-f047-4cdb-a6c0-ccc5f70cb5a0">

<img width="784" alt="Screenshot 2024-01-27 at 5 33 19 PM" src="https://github.com/LC0229/cse15l-lab-reports/assets/156004283/3fa7cc70-4ca0-4687-b92b-51a0bb99a6bc">

<img width="777" alt="Screenshot 2024-01-27 at 5 28 50 PM" src="https://github.com/LC0229/cse15l-lab-reports/assets/156004283/105465ae-6734-4b84-81a8-65d7bcf22b69">


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

          return "404 Not Found!"; 
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
    Firstly, let's start with the process of compiling. For starting the server, we need to `cd` our working directory to wavelet for accessing 
    Server.java and ChatServer.java files, then we may compile both by using `javac` and put both as arguments. The reason we need Server.java 
    is that it provides the method called `start` for us to start a server by putting port number and URLHandler as arguments. It helps us to 
    create a website page with functions we created in ChatServer.java. For this ChatServer file, it imports `java.io` and `java.net` classes 
    from standard library in java for handling Input/output(`IOException`) and dealing with URL(`URI`). Then we start our class class called 
    Handler, which implements URLhandler interface for us override HandRequest method in it. We starts wtih creating an String variable called
    `result`, which will be responsible to store all contents we input to the website. For overriding the HandRequest method, we put URL as an     
    argument, which help us to investigate and modify the content of website. We created a String variable called query, by calling `.getQuery()` 
    to store the query of the URL. Since we are trying to handle `/add-message` command, we check the Path of URL if it is `/add-message`. 
    In the result of `if` statement is true, we starts with creating a String variable called `param` by splitting the query with `&`, because we   
    expect the query in the format of `s=<string>&user=<string>`. This is also the reason why we need to check if the length of param is 2, `param[0]`
    starts with `s=`, `param[1]` starts with `user=`. For fulfilling the format, we expect `param[0]` be `s=<string>` and `param[1]` be 
    `user=<string>`, and only one `&` exists in the query. 