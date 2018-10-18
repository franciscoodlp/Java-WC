import java.io.*;
   
public class WordCount {
   
      public static void main(String[] args) throws Exception {
         
         File file = new File(args[0]);
         
         BufferedReader reader = new BufferedReader(new FileReader(file));       
            
            String s = reader.readLine();
            int line_Count = 0;
            while(s != null) {
               line_Count++;
               s = reader.readLine();
            }
         System.out.println(line_Count);
         
         reader = new BufferedReader(new FileReader(file));
            int char_Count = 0;
            while(reader.read() != -1) {
               char_Count++;
            }
            System.out.print(char_Count);       
      }
      
}         
        
