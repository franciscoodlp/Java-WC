import java.io.*;
import java.util.*;
   
public class WordCount {
   
      public static void main(String[] args) throws Exception {
      
      try {
      
         if (args.length == 0) {
            help_Message();
         } else {   
         file_Counter(args, parse_Args(args));
         }
      }
      
      catch(Exception e) {
      
         help_Message();
         System.exit(1);
      
      }
      
      }
      
      public static void file_Counter(String[] args, int x) throws Exception {
         int line_Count = 0;
         int char_Count = 0;
         int word_Count = 0;
         int maxL = 0;
         int maxW = 0;
         int maxC = 0;
                  
         int i = 0;
         if (x == 1 || x == 2  || x == 3) {
            i = 1;
         } else if(x == 4) {
            i = 0;
         } else {
            i = 1;
         }       
         
         if(args.length > 0) {
         
         for (int z = i; z < (args.length) ; z++) {
                  
         File file = new File(args[i]);
         
         BufferedReader reader = new BufferedReader(new FileReader(file));        
            String s = reader.readLine();
            while(s != null) {
               line_Count++;
               maxL ++;
               s = reader.readLine();
            }
         
         reader = new BufferedReader(new FileReader(file));  
            String c = reader.readLine();
            while(c != null) {
               String[] words = c.split(" ");
               for (String word : words) {
                  char_Count += word.length();
                  maxC += word.length();
               }
               c = reader.readLine();   
            }
         
         reader = new BufferedReader(new FileReader(file));
            String k;
             while ((k = reader.readLine()) != null) {
               String[] words = k.split(" ");
               word_Count += words.length;
               maxW += words.length;  
            }             
         
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
         } else if(x == 5) {
         System.out.print(" Max line count = " + maxL);                 
         } else if(x == 6) {
         System.out.print("Max character count = " + maxC);
         } else if(x == 7) {
         System.out.print("Max word count = " + maxW);
         } else if(x == 8) {
         System.out.println("Max line count = " + maxL);
         System.out.println("Max character count = " + maxC);
         System.out.print("Max word count = " + maxW);                 
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
         if (args.length > 0 && args.length <= 2) {
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
         } else if(args.length > 2) {
            s = args[0];
            if (s.contains("-l")) {
               return i = 5;
            } else if (s.contains("-c")) {
               return i = 6;
            } else if (s.contains("-w")) {
               return i = 7;
            } else {
               return i = 8;
            }

         }
         return i;             
      }
       
}                         
