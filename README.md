package java;

import java.util.Random;
public class activity 
{

	public static void main(String[] args) {
		PetShop pets = new PetShop();
		pets.runApplication();
	}

}

abstract class Pet {
	public String petName;
	public int petStrength;

	public Pet() {
		Random rand1 = new Random();
		petStrength =  rand1.nextInt(100);

	}
	    
	}

class PetShop{
	public void runApplication() {
		
		System.out.println("numberOfDogWinners : " + this.doCompetition()[0]);
		System.out.println("numberOfCatWinners : " + this.doCompetition()[1]);
		
	}
	
	public int[] doCompetition() {
		int[] returnValues = new int[2];
		int numberOfDogWinners = 0;
		int numberOfCatWinners = 0;
		
		for (int i = 0; i<10; i++) {

			if ((new Dog()).petStrength > (new Cat()).petStrength) {
				numberOfDogWinners++;
			}
			else {
				numberOfCatWinners++;
			}
		}
		
		if (numberOfDogWinners > numberOfCatWinners) {
			returnValues[1] = numberOfDogWinners;
			returnValues[0] = numberOfCatWinners;
		}
		else 
		{
		
		returnValues[0] = numberOfDogWinners;
		returnValues[1] = numberOfCatWinners;}
		return returnValues;

	}
	
}

class Dog extends Pet{

}

class Cat extends Pet{
	
}
