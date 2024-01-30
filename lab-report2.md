
<img width="784" alt="Screenshot 2024-01-27 at 5 33 54 PM" src="https://github.com/LC0229/cse15l-lab-reports/assets/156004283/219dd894-f047-4cdb-a6c0-ccc5f70cb5a0">

<img width="784" alt="Screenshot 2024-01-27 at 5 33 19 PM" src="https://github.com/LC0229/cse15l-lab-reports/assets/156004283/3fa7cc70-4ca0-4687-b92b-51a0bb99a6bc">

<img width="777" alt="Screenshot 2024-01-27 at 5 28 50 PM" src="https://github.com/LC0229/cse15l-lab-reports/assets/156004283/105465ae-6734-4b84-81a8-65d7bcf22b69">

```java
import java.io.IOException;
import java.net.URI;
import java.util.List;




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
