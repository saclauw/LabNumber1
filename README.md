#LabNumber1


import java.util.Scanner; // imported the scanner to read the user input

public class LabNumber1 {

	public static void main(String[] args) {

		double roomLength = 0.0; // double variables declared for user input
		double roomWidth = 0.0;
		double roomHeight = 0.0;
		boolean isLengthNum; // boolean used to validate the user input
		boolean isWidthNum;
		boolean isHeightNum;
		String a; // String a is used for do while loop to continue the application

		Scanner scanner = new Scanner(System.in); // scanner initiliazed

		System.out.println("Welcome to Grand Circus' Room Detail Generator!");

		do { // first do to encompass all three do while loops to ultimately ask continue, while y
			do { // this do while loop is to get the length from the user and validate their input
				System.out.println("Enter Length: ");
				if (scanner.hasNextDouble()) { // if their input is a number it will continue to the next loop
					roomLength = scanner.nextDouble();
					isLengthNum = true;
				} else { // if their input if not a number this loop restarts
					System.out.println("That is not a number. Please enter a number: ");
					isLengthNum = false;
					scanner.next();
				}
			} while (!(isLengthNum));

			do { // this do while loop is to get the width from the user and validate their input
				System.out.println("Enter Width: ");
				if (scanner.hasNextDouble()) {
					roomWidth = scanner.nextDouble();
					isWidthNum = true;
				} else {
					System.out.println("That is not a number. Please enter a number: ");
					isWidthNum = false;
					scanner.next();
				}
			} while (!(isWidthNum));

			do { // this do while loop is to get the height from the user and validate their input
				System.out.println("Enter Height: ");
				if (scanner.hasNextDouble()) {
					roomHeight = scanner.nextDouble();
					isHeightNum = true;
				} else {
					System.out.println("That is not a number. Please enter a number: ");
					isHeightNum = false;
					scanner.next();
				}
			} while (!(isHeightNum));

			System.out.println("Area: " + roomLength * roomWidth); //Area calculated by multiplying length by width
			System.out.println("Perimeter: " + ((roomLength * 2) + (roomWidth * 2))); // Perimeter calculated by adding length*2 and width*2 they are in parentheses to ensure the double adds correctly
			System.out.println("Volume: " + (roomHeight * roomLength * roomWidth)); // Volume calculated by multiplying height by width by length

			System.out.println("Continue? (y/n): "); // loop ends with asking the user if they would like to continue
			a = scanner.next();
		} while ((a.equals("y")) || (a.equals("Y"))); // only if the input is y or Y will the loop continue

		scanner.close();
	}
}
