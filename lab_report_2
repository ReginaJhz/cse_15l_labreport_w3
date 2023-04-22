# Servers and Bugs

## Part 1 Web Server

The following code is an implementation of StringServer.

```
import java.io.IOException;
import java.net.URI;

  class Handler implements URLHandler {
    StringBuilder message = new StringBuilder("");

    public String handleRequest(URI uri) throws RuntimeException {
        if (uri.getPath().equals("/")) {
            return "Out content is none";
        } else {
            System.out.println("Path: " + uri.getPath());
            if (uri.getPath().contains("/add-message")) {
                String[] parameters = uri.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    message.append(parameters[1]);
                    message.append("\n");
                }
                return message.toString();
            }
        }
        return "404 Not Found!";
    }
    
    public class StringServer{
        public static void main(String[] args) throws IOException{
            if(args.length == 0){
                System.out.println("missing port number");
                return;
            }
            int portNumber = Integer.parseInt(args[0]);
            Server.start(portNumber, new Handler());
            }
    }
}
```
