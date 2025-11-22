package project;
import java.util.Scanner;
public class LibraryManagmentSystem {

    static String[] Books = new String[100];
    static int count = 0;

    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);
    

        while(true){
            System.out.println("<--Library Managment System -->");
        System.out.println("====== Library Menu ======");
        System.out.println("Select One Option");
        System.out.println("1.Add Books");
        System.out.println("2.View Book");
        System.out.println("3.Search Book");
        System.out.println("4.Remove Book");
        System.out.println("5.Totals Book");
        System.out.println("6.Exit");
        System.out.println("Enter your choice: ");

        int str = sc.nextInt();
        sc.nextLine();
      


        if (str == 1 ){
            System.out.println("Emter Book Name: ");
            String name =sc.nextLine();
            Books [count] = name;
            count++;
            System.out.println("Books added sucesfully.");


        }else if (str == 2){
            System.out.println("==== Books list ==== ");
            if(count == 0){
                System.out.println("no books availabe.");
            }else {
                for(int i = 0  ; i < count ; i++ ){
                    System.out.println((i+1) + " : " + Books[i]);
                }
            }


            
        }else if (str==3){
            System.out.println("Enter book to Search: ");
            String input =sc.nextLine();

            boolean found = false;
            
            for(int i = 0;i<count;i++){
                if(Books[i].equalsIgnoreCase(input)){
                    System.out.println("Books is available at position number: "+ (i+1));
                    found = true;
                    break;
                }
            }
            if(!found){
                System.out.println("Book not found.");
            }


        }else if (str==4){
            System.out.println("Enter book number to remove: ");
            int num = sc.nextInt();
            

            if (num <1 || num > count ){
                System.out.println("Invalid number.");
            }else{

                int index = num - 1;

            for(int i = index ; i < count -1; i++){
                 Books[i] = Books[i + 1];
            }
            Books [count -1] = null;
            count--;
            System.out.println("Book removed sucessfully.");

            }
            

        }else if (str==5){
            System.out.println("<-<-<- books list ->->->");
           System.out.println("Total books is: " + count);


        }else if (str==6){
            System.out.println("Exit");
            break;

            
        }else{
            System.out.println("Invalid");
        }
        }
      sc.close();
    }
    
    
}

