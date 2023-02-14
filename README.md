# Simple-Login

import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        String enteredPassword = "", newPassword = "";
        String password = "mypass";

        boolean isPasswordCorrect = false;

        Scanner scanner = new Scanner(System.in);

        System.out.println("Enter password: ");
        enteredPassword = scanner.nextLine();

        if(enteredPassword.equals(password))
        {
            System.out.println("Password is correct! You entered to the system.");
        }
        else
        {
            System.out.println("Password is incorrect! Do you want to reset the password? \n Press 1 to reset \n Press 2 to exit");
            int choice = scanner.nextInt();

            switch (choice)
            {
                case 1:
                    resetPassword(password, newPassword);
                    break;
                case 2:
                    System.out.println("Program terminated.");
                    break;
                default:
                    System.out.println("An error occurred!");
                    break;
            }
        }

    }

    public static void resetPassword(String oldPassword, String newPassword){
        Scanner scanner = new Scanner(System.in);
        System.out.println("Enter the new password: ");
        newPassword = scanner.nextLine();
        if(newPassword.equals(oldPassword)){
            System.out.println("The new password cannot be the same as your old password!");
        }
        else{
            oldPassword = newPassword;
            System.out.println("Password changed successfully!");
        }
    }
}
