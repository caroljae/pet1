# pet1
**Java Pet Boutique Main File College Project
package pet;
import java.util.Scanner;
import java.text.DecimalFormat;

public class PetMain 
{
	public static void main(String[] args) 
	{
		Scanner input = new Scanner(System.in);
		
		//Create copy of all classes for use 
		Customer myCustomer = new Customer();
		Pet myPet = new Pet();
		ServiceCharge myCharge = new ServiceCharge();	
		DecimalFormat dollar = new DecimalFormat("#,##0.00");
						
		//Customer information
		System.out.println("Enter the customer's name: ");
		String name = input.nextLine();
    
		//Call method to transfer info to the class
		myCustomer.setName(name);
		
		System.out.println("Enter the customer's address: ");
		String address = input.nextLine();
		myCustomer.setAddress(address);
		
		System.out.println("Enter the customer's phone number: ");
		String phone = input.nextLine();
		myCustomer.setPhone(phone);
		
		System.out.println("Enter the customer's email address: ");
		String email = input.nextLine();
		myCustomer.setEmail(email);		
		
		//Pet information
		System.out.println("Enter the name of the pet: ");
		String petname = input.nextLine();	
    
		//Call method to transfer info to the class
		myPet.setPetname(petname);
				
		System.out.println("Enter the pet type: ");
		String pettype = input.nextLine();
		myPet.setPettype(pettype);
				
		System.out.println("Enter the age of the pet: ");
		String petage = input.nextLine();
		myPet.setPetage(petage);
		
		System.out.println("Enter the weight of the pet: ");
		String petweight = input.nextLine();
		myPet.setPetweight(petweight);
		
		//Service Charge information
		System.out.println("Enter the charge for services rendered: ");
		double services = input.nextDouble();
    
		//Loop to check parameters
		while (services <= 0)
		{
			System.out.println("Charges must be greater than zero.");
			System.out.println("Please try again.");
			services = input.nextDouble();
		}
    
		//Call method to transfer info to the class
		myCharge.setServices(services);
				
		System.out.println("Enter the charge for medication: ");
		double meds = input.nextDouble();
    
		//Loop to check parameters
		while (meds <= 0)
		{
			System.out.println("Charges must be greater than zero.");
			System.out.println("Please try again.");
			meds = input.nextDouble();
		}
		myCharge.setMeds(meds);
		
		//Display information
		System.out.println("*********The Pet Boutique**********");
		System.out.println("Customer Name: " + myCustomer.getName());
		System.out.println("Address: " + myCustomer.getAddress());
		System.out.println("Phone: " + myCustomer.getPhone());
		System.out.println("Email: " + myCustomer.getEmail());
		System.out.println("Pet Name: " + myPet.getPetname());
		System.out.println("Pet Type: " + myPet.getPettype());
		System.out.println("Pet Age: " + myPet.getPetage());
		System.out.println("Pet Weight: " + myPet.getPetweight());
		System.out.println("Service Charge: $" + dollar.format(myCharge.getServices()));
		System.out.println("Medication Charge: $" + dollar.format(myCharge.getMeds()));
		System.out.println("Sales Tax: $" + dollar.format(myCharge.getSalesTax()));
		System.out.println("Total: $" + dollar.format(myCharge.getTotal()));
	}
}
