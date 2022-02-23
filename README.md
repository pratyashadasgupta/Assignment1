# Assignment1

Q1. We know a subclass does not inherit private members of its superclass. In the above example the class A only has two private constructors , therefore it's subclass cannot be created.

Q2. Yes. As we know a subclass inherits protected and public members of its superclass.

Q3. As the inner class B in the above code is private its instance cannot be made outside of the class A. Therefore this code will give an error.

Q4. Class A has no access modifier i.e default. We know the default access modifier makes the class only visible within the same package but not to other packages. Therefore class A cannot have subclass outside it's own package.

Q5. Classes cannot be declared as protected. If we try to do so it will give a compile error. However inner classes can be declared as private.

Q6. The above code is correct.
    Output: 1221
            1221

Q7. This program will not work. Class A has no access modifier i.e default. We know the default access modifier makes the class only visible within the same package but not to other packages. Therefore class A cannot have its instance created outside it's own package.

Q8. The accessibility of the protected field is within its own package and in a subclass of any other package. Therefore it can be inherited.

Q9. In the above code , class A has a protected constructor. As we know protected members can be accessed within the same package and in a subclass in another pacakge. In this code class B does not extend class A , therefore when we try to create an instance of class A(which has a protected constructor) it throws an error.

Q10. Yes we can have private static methods. But as private members cannot be accessed outside the class therefore it is better not to use private static methods.

Q11. The output will be 104.

Q12. In this code snippet the accessibility of methodOfA has been reduced from public to default which is not allowed which throws the error.

Q13. False. Private methods are not inherited therefore cannot be overriden in subclass.

Q14. True. Default methods of parent class can be overriden as public or protected because we are increasing the accessibility. But if try to override it as private we decrease the accessbility which is not allowed.

Q15.

package assignment;

public class Employee {
	public String name;
	public String address;
	private double salary;
	public int id;


	Employee(String name , String address , double salary , int id){
		this.name = name;
		this.address = address;
		this.setSalary(salary);
		this.id = id;
	
	}


	public double getSalary() {
		return salary;
	}


	public void setSalary(double salary) {
		this.salary = salary;
	}
	
	public String toString() {
		return "Employee[Name- " + name + " , Address- " + address + " , Salary- " + salary + " , ID - " + id + "]";
	}
}


public class HR extends Employee {

	HR(String name, String address, double salary, int id) {
		super(name, address, salary, id);
		// TODO Auto-generated constructor stub
	}
	
	public void calculatesalary() {
		double s;
		s = getSalary();
	    s = s + 0.1*s;
		System.out.println("The incremented salary of "+ this.name + " is "+ s);
	}
	
	
	public static void main(String[] args) {
		HR CEO = new HR("Rajesh Kumar","SaltLake,Kolkata",70000 , 1);
		System.out.println(CEO);
		CEO.calculatesalary();
		
		HR ProjectManager = new HR("Saurav Chaudhuri","Newtown", 50000 , 2);
		System.out.println(ProjectManager);
		ProjectManager.calculatesalary();
		
		HR teamlead = new HR("Sahil Nagpal","Santoshpur", 30000 , 3);
		System.out.println(teamlead);
		teamlead.calculatesalary();
	}
}
