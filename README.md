import java.io.*;
import java.util.*;
   
public class WordCount {
   
      public static void main(String[] args) throws Exception {
      
      if (args.length == 0) {
         help_Message();
      } else {   
      file_Counter(args, parse_Args(args));
      }
      
      }
      
      public static void file_Counter(String[] args, int x) throws Exception {
         
         int i = 0;
         if (x == 1 || x == 2  || x == 3) {
            i = 1;
         } else {
            i = 0;
         }       
         
         if(args.length > 0) {
          
         File file = new File(args[i]);
         
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
         System.out.print("Line count = " + line_Count);
         } else if(x == 2) {
         System.out.print("Character count = " + char_Count);
         } else if(x == 3) {
         System.out.print("Word count = " + word_Count);
         } else if(x == 4) {
         System.out.println("Line count = " + line_Count);
         System.out.println("Character count = " + char_Count);
         System.out.print("Word count = " + word_Count);                 
         }
         
         }
                      
      }
      
      public static void help_Message() {
         
         System.out.println("java wc <Insert File(s)>");
         System.out.println("-c will print the character count");
         System.out.println("-l will print the line count");
         System.out.println("-w will print the word count");
         System.out.print("-h will print this help message");
      
      }
      
      public static int parse_Args(String[] args) {
         int i = 0;
         String s;
         if (args.length > 0) {
            s = args[0];
            if (s.contains("-l")) {
               return i = 1;
            } else if (s.contains("-c")) {
               return i = 2;
            } else if (s.contains("-w")) {
               return i = 3;
            } else {
               return i = 4;
            }
         } else {
            return i;
         }             
      }
       
}         
                            
