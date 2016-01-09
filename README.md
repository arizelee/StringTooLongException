# StringTooLongException
This program creates an exception class to note when a String is over 20 characters in length.

package Exceptions.HW;

import java.util.Scanner;

public class EnterString2 {
    
    public static void main(String [] args) throws StringTooLongException {
        
        StringTooLongException exception = new StringTooLongException("Excess of characters.");
        
        Scanner entry = new Scanner(System.in);
        System.out.println("Enter a statement no longer than 20 characters: ");
        String s = (String) entry.nextLine();
        
        while(!s.equals("DONE")) {
            try{
                if (s.length() <= 20) {
                } else {
                    throw exception;
                }
            }          
            catch(StringTooLongException e){
                System.out.println ("The entry, " + s + ", has too many characters.");
            }
        System.out.println("Enter a statement no longer than 20 characters: ");
        s = (String) entry.nextLine();
       }
    }
}
_____________________________________________________________________

public class StringTooLongException extends Exception{
    
    public StringTooLongException(String m){
            super(m);
            
    }
}
