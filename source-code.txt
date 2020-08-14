import java.util.*;
import java.io.*;
class main {

public static void main(String args[]) throws IOException  
{
    int option = 0;
    String sentence = "",answer = "",answer1 = "";
     char[] english = { 'a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l',
             'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 
             'y', 'z', '1', '2', '3', '4', '5', '6', '7', '8', '9', '0',
             ',', '.', '?' };   

     String[] morse = { ".-", "-...", "-.-.", "-..", ".", "..-.", "--.", "....", "..", 
                ".---", "-.-", ".-..", "--", "-.", "---", ".---.", "--.-", ".-.",
                "...", "-", "..-", "...-", ".--", "-..-", "-.--", "--..", ".----",
                "..---", "...--", "....-", ".....", "-....", "--...", "---..", "----.",
                "-----", "--..--", ".-.-.-", "..--.." };    
    Scanner sc = new Scanner(System.in);
    BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
    System.out.print("\n");
    System.out.println(">>This software converts text to morse code and vice-versa<<");
    System.out.println("");
    do
    {
    System.out.println("-->Enter the Required option ");
    System.out.println("1. English text to Morse\n2. Morse to English\n3. Exit ");
    System.out.print("->");
    while(!sc.hasNextInt()) 
    {
    	    System.out.println("");
        System.err.println("-->ERROR<-->Check your input<--");
        System.out.print("->");
        sc.next();  
    }
    option = sc.nextInt();
    switch(option)
    {
    case 1:
    {
        System.out.println("");
        System.out.println("-->Enter the Text that you want to convert to Morse Code ");
        System.out.print("->");
        sentence = br.readLine();
        System.out.println("");
        sentence = sentence.toLowerCase(); 
        char[] morsec = sentence.toCharArray();
        for(int i = 0; i < morsec.length;i++)   
        {
            for(int j = 0;j<english.length;j++)   
            {
                if(english[j] == morsec[i]) { 
                    answer = answer + morse[j] + " ";  
                }  
            }
        }
        System.out.println("-->The Morse Code for the given text is:- ");
        System.out.print(">> ");
        System.out.println(answer);
        System.out.println("");
        answer = "";
	break;
    }
    case 2:
    {
        System.out.println("");
        System.out.println("-->Enter the Morse Code (After Every Letter add Space in Between) ");
        System.out.print("-> ");
        sentence = br.readLine();
        System.out.println("");
        String[] morsec = sentence.split(" ");  
        for(int i = 0;i < morsec.length;i++)
	{    
            for(int j = 0;j < morse.length;j++)
            {
                if(morse[j].equals(morsec[i]))                 {
                    answer1 = answer1 + english[j];
                }
            }
        }
        System.out.println("-->The English Translation is:- ");
        System.out.print(">> ");
        System.out.println(answer1);
        System.out.println("");
        answer1 = "";
	break;
    }
    case 3:
    {
        System.out.println("");
        System.out.println("Thank you");
        System.out.println("");
        break;
    }
    default:
    {
        System.err.println("-->ERROR<-->Invalid Option Entered<--");
        System.out.println("");
        break;
    }
    }
    }
    while(option!=3);
    }
}
