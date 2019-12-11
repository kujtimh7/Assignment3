import java.util.*;
import java.io.*;

public class Song{
	private static HashMap<String, Integer> frequency = new HashMap<>();
    /*I used a HASHMAP to organize the use between each word and the number of times it was used
     *Any time a word is counted a second time and onwards we reimplement
     * it but by adding one to the value, as seen in the following method.
*/
	
	//This method accepts a line of text from a txt file and removes (),?,! and commas in order to prevent miscounting
    public static void countTheWords(String lyrics){
   
    	 lyrics=lyrics.replace("(", "");
    	 lyrics=lyrics.replace(",","");
    	 lyrics=lyrics.replace(")", "");
    	 lyrics=lyrics.replace("!", "");
    	 lyrics=lyrics.replace("?", "");
        String[] words =lyrics.toLowerCase().split(" ");
        //here 'words' is used to store all the words in the line, using spaces to dictate where each word is.
        
        for(String a: words) {
        if(!frequency.containsKey(a)) {//Here is a check if a word is new or already in the HASMAP
        	frequency.put(a,1) ;//if the word is new, add it with a count of one
         }
        else {
        	frequency.put(a,frequency.get(a)+1);//if the word has bee seen, add one
        }
        
        
        }
    }
       
    /*This makes the map in order to ensure that printing is easier and to ensure it's printed from greatest to least
     * It accept a Set string and converts it to an array to make changing the order easier. 
     */
    public static String[] makeInOrder(Set<String> keys){
       
      String[] ord= new String[keys.size()];
      keys.toArray(ord);
   
        String temp="";
        
        for(int i=1; i< ord.length;i++) {
        	 int j = i;
        	   while (j > 0 && frequency.get(ord[j]) > frequency.get(ord[j-1])) {
        		   temp = ord[j];
        		     ord[j] = ord[j-1]; //I chose to do a insertion sort because it's the one I'm most familiar with.
        		     ord[j-1] = temp;
        	      j--;
        	   }
        
        	  }
        
        return ord;
        
    }
    //This is where the HASHmap is finally printed with the format "count: word"
    public static void printOrder(String[] arr) {
    	
    	for(String word: arr){
            System.out.println(frequency.get(word)+": "+word);
        }

    }
    

    public static void main(String[] args){
//the new file is read
        File file = new File("lyrics.txt");
        try{
            Scanner sc = new Scanner(file);
            String lyrics;
            while(sc.hasNextLine()){
                lyrics = sc.nextLine();
                //each line of txt is read,counted, and added to the hashmap
                countTheWords(lyrics);
            }
            
           String[] allWords = makeInOrder(frequency.keySet());//turn the key set into an array, make them in order and then print them
           printOrder(allWords);
  
        }
        catch(FileNotFoundException E){
            System.out.println("File not found");
        }
    }
}
