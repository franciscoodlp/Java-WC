import java.io.*;
import java.util.*;
   
public class WordCount {
   
      public static void main(String[] args) throws Exception {
      
      fileCounter(args, 4); 
      
      }
      
      public static void fileCounter(String[] args, int x) throws Exception {
          
         File file = new File(args[0]);
         
         BufferedReader reader = new BufferedReader(new FileReader(file));        
            String s = reader.readLine();
            int line_Count = 0;
            while(s != null) {
               line_Count++;
               s = reader.readLine();
            }
         
         reader = new BufferedReader(new FileReader(file));  
            int char_Count = 0;
            String c = reader.readLine();
            while(c != null) {
               String[] words = c.split(" ");
               for (String word : words) {
                  char_Count += word.length();
               }
               c = reader.readLine();   
            }
         
         reader = new BufferedReader(new FileReader(file));
            String k;
            int word_Count = 0;
            while ((k = reader.readLine()) != null) {
            String[] words = k.split(" ");
            word_Count += words.length;  
            }
         
         if (x == 1) {
         System.out.println("Line count = " + line_Count);
         } else if(x == 2) {
         System.out.println("Character count = " + char_Count);
         } else if(x == 3) {
         System.out.println("Word count = " + word_Count);
         } else if(x == 4) {
         System.out.println("Line count = " + line_Count);
         System.out.println("Character count = " + char_Count);
         System.out.print("Word count = " + word_Count);                 
         }
           
      } 
}         
                  
