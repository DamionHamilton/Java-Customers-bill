Java-Customers-bill
===================

Java codeing (Calculates customers bill for family meal)

// Damion Hamilton
// Customer Bill

package java_customer_bill;
import java.util.Scanner;
import java.lang.*;
import java.io.*;
import java.math.*;
import java.text.DecimalFormat.*;
import java.lang.String.*;
import javax.swing.JOptionPane;
/**
 *
 * @author Damion
 */
public class Java_Customer_bill {

    /**
     * @param args the command line arguments
     */
  
    
    public static void main(String[] args) {
        
       
        Scanner console = new Scanner (System.in);
        
        int number;
        System.out.println(" This program will perduce Customer bills");
        System.out.println("");
        
        int child_count, adult_count;
        double adult_cost, child_cost, dessert_cost, room_rate, deposit, food_cost,
                total_due, total_dessert_cost, total_cost_adult, total_cost_child, 
                total_food_cost, total_due2, tip_tax, percentage;
        
        // The following code takes the user input and assigns input to variable
        
        System.out.println("Enter number of children to be served");
        child_count = console.nextInt();
        
        System.out.println("Enter number of adults to be served");
        adult_count = console.nextInt();
        
        System.out.println("Enter cost per adult meal");
        adult_cost = console.nextDouble();
        
        System.out.println("Ener cost for dessert");
        dessert_cost = console.nextDouble();
        
        System.out.println("Enter cost for room");
        room_rate = console.nextDouble();
        
        System.out.println("Enter tip and tax percentage");
        percentage = console.nextDouble();
        
        System.out.println("Enter Deposit");
        deposit = console.nextDouble();
        
        // Following code fills selected variable with appropriate data 
        // Cost per child is %60 less than cost of adult meal
        
        child_cost = .60*adult_cost;
        food_cost = child_count*child_cost + adult_count*adult_cost + dessert_cost;
        total_dessert_cost=(child_count+adult_count)*dessert_cost;
        total_cost_adult = adult_count * adult_cost;
        total_cost_child = child_count * child_cost;
        total_food_cost = (adult_count * adult_cost) + (child_count * child_cost) + (total_dessert_cost);
        total_due2 = total_cost_adult + total_cost_child + total_dessert_cost;
        tip_tax = total_food_cost * percentage;
        total_due = total_food_cost + tip_tax + room_rate;
        
        //Following code outputs processed data
        
        System.out.println(String.format("Cost per Child:"+" " + "$" + '\t'+"%.2f%n", child_cost));
        System.out.println(String.format("Total cost for Adults:"+" " + "$" + '\t'+"%.2f%n", adult_count * adult_cost));
        System.out.println(String.format("Total cost for Children:"+" " + "$" + '\t'+"%.2f%n", child_count * child_cost));
        System.out.println(String.format("Total cost for Dessert:"+" " + "$" + '\t'+"%.2f%n", (child_count + adult_count) * dessert_cost));
        System.out.println(String.format("Total cost for Meal:"+" " + "$" + '\t'+"%.2f%n", total_food_cost));
        System.out.println(String.format("Tip/Tax:"+" " + "$" + '\t'+"%.2f%n", tip_tax));
        System.out.println(String.format("Room Charges:"+" " + "$" + '\t'+"%.2f%n", room_rate));
        System.out.println(String.format("Total Due:"+" " + "$" + '\t'+"%.2f%n", total_due + room_rate));
        System.out.println(String.format("Deposit:"+" " + "$" + '\t'+"%.2f%n", deposit));
        System.out.println(String.format("Total Balance Due:"+" " + "$" + '\t'+"%.2f%n", total_due - deposit));
        
        
        
    }
}

