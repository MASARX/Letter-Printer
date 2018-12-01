# Letter-Printer
Prints X,Y,W,Z letters with stars.

      import java.util.Scanner;
      //Letter Printer Program
      public class Pro3_2_150116011 {

        public static void main(String[] args) {
          System.out.println("Welcome to letter printer program.");
          while(true) { // We started with infinite loop to start again if user want to continue when program is done.
          Scanner sc = new Scanner(System.in);
          System.out.println("Enter the size: ");
              int size = sc.nextInt(); //Getting size information from user.

              while(size%2==0 || size<5) {
                System.out.println("Invalid size. Enter the size again: ");
                size = sc.nextInt(); // If size is even or smaller than 5, size is invalid so user has to enter the size again.
              }

              String letter;
              Scanner lt = new Scanner(System.in);
              System.out.println("Enter the letter: ");
              letter=lt.nextLine(); //Getting letter. I accept only lower case.

              while(true) {
                if(letter.equals("x") || letter.equals("y") || letter.equals("z") || letter.equals("X") || letter.equals("Y") || letter.equals("Z") || letter.equals("w") || letter.equals("W")) {
                  break;
                }
                System.out.println("Invalid letter. Enter the letter again: ");
                letter = lt.nextLine();
              } // We control the letter here. If it is invalid, user has to enter again.

              switch(letter) { // We use switch-case to make letters pattern.
              case "x":
              case "X":
                for (int satir = 0; satir < size; satir++) {
                    for (int sutun = 0; sutun < size; sutun++) {
                        if (satir == sutun || sutun == (size - 1 - satir))
                            System.out.print("*");
                        else
                            System.out.print(" ");
                    }
                    System.out.println();
                } //This case for x letter.
                break;
              case "z":
              case "Z":
                for (int satir = 0; satir < size; satir++) {
                      for (int sutun = 0; sutun < size; sutun++) {
                          if (satir == 0 || satir == size - 1 || sutun == size - 1 - satir) {
                              System.out.print("*");
                          } else {
                              System.out.print(" ");
                          }
                      }
                      System.out.println();
                  }//This case for z letter.
                break;
              case "y":
              case "Y":
                for(int satir=1;satir<=size;satir++){
                  for(int sutun=1;sutun<=size;sutun++){
                    if((sutun==(size/2)+1 && satir>=(size/2)+1) || sutun==(size-satir+1) && satir<=(size/2) || (satir==sutun && sutun<=(size/2))){
                      System.out.print("*");
                    }
                    else{
                      System.out.print(" ");
                    }
                  }
                  System.out.println();
                }//This case for y letter.
                break;
              case "w":
              case "W":
                int width= (size*4)-3;
                for(int satir =1; satir <= size; satir++) {
                  for(int sutun=1; sutun<=width; sutun++) {
                    if((satir==sutun) || (satir+(width/2)==sutun) || sutun==(size*2)-satir || sutun==(size*2)-satir+(width/2) ) {
                      System.out.print("*");
                    }
                    else {
                      System.out.print(" ");
                    }
                  }
                  System.out.println();
                }
              }
              System.out.println("Would you like to continue? ( Y or N): ");
              Scanner sc1 = new Scanner (System.in);
              String cnt = sc1.nextLine();
              if(cnt.equals("n") || cnt.equals("N")){
                break;
              }//If users answer is n for no, this break will finish the infinite while loop at the beginning.
          }
        }
      }
