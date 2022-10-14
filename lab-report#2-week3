**#CODE FOR SEARCH ENGINE#**

'
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList; // import the ArrayList class

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    ArrayList<String> stringsAdded = new ArrayList<String>(); // Create an ArrayList object
    ArrayList<String> stringsFound = new ArrayList<String>();

    public String handleRequest(URI url) {
        System.out.println("Path: " + url.getPath());
        if (url.getPath().contains("/add")) {
            String[] parameters = url.getQuery().split("=");
            if (parameters[0].equals("s")) {
                stringsAdded.add(parameters[1]);
                return String.format("String is added to list!");
            }
            else {
                return String.format("Please input correctly");
            }
        }
        
        if (url.getPath().contains("/search")) {
            String[] parameters = url.getQuery().split("=");
            if (stringsAdded.size()==0){
                return String.format("You must add a string first!!!");
            }
            else{
                for(int i=0; i<stringsAdded.size(); i++) {
                    if ((stringsAdded.get(i)).contains(parameters[1])){
                        stringsFound.add(stringsAdded.get(i));
                    }
                }
                return String.format("Strings Found" + stringsFound);
            }
        }
        else {
            return "error";
        }
}
}



class SearchEngine {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
'



