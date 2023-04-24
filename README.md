

import java.util.Scanner;

public class HotelManagementSystem {

    // Array to store hotel rooms
    private static String[][] rooms = new String[10][2];
    private static Scanner scanner = new Scanner(System.in);

    public static void main(String[] args) {
        // Initialize hotel rooms
        for (int i = 0; i < rooms.length; i++) {
            rooms[i][0] = String.valueOf(i + 1);
            rooms[i][1] = "Empty";
        }

        // Display hotel menu
        while (true) {
            System.out.println("\nWelcome to the Hotel Management System\n");
            System.out.println("1. Check-In");
            System.out.println("2. Check-Out");
            System.out.println("3. View Occupancy");
            System.out.println("4. Exit");
            System.out.print("\nEnter your choice: ");

            int choice = scanner.nextInt();

            switch (choice) {
                case 1:
                    checkIn();
                    break;
                case 2:
                    checkOut();
                    break;
                case 3:
                    viewOccupancy();
                    break;
                case 4:
                    System.exit(0);
                    break;
                default:
                    System.out.println("\nInvalid choice. Please try again.");
                    break;
            }
        }
    }

    // Method to check-in guests
    private static void checkIn() {
        System.out.print("\nEnter room number: ");
        int roomNumber = scanner.nextInt() - 1;

        if (roomNumber >= 0 && roomNumber < rooms.length) {
            if (rooms[roomNumber][1].equals("Empty")) {
                System.out.print("\nEnter guest name: ");
                String guestName = scanner.next();
                rooms[roomNumber][1] = guestName;
                System.out.println("\nCheck-in successf
