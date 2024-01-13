import java.util.Scanner;

public class Task04 {
    private static final int roomsCount = 5;
    private static final int[] roomNumbers = new int[roomsCount];
    private static final String[] roomCategories = new String[roomsCount];
    private static final boolean[] roomAvailability = new boolean[roomsCount];

    static {
        initializeRooms();
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.println("Welcome! Please Enter:\n\"1\" To Search For Available Rooms\n\"2\" To Make A Reservation\n\"3\" To View Booking Details\n\"4\" To Exit");
        int choice = scanner.nextInt();

        while (choice!=4) {
            switch (choice) {
                case 1:
                    System.out.println("Available Rooms:");
                    AvailableRooms();
                    break;
                case 2:
                    System.out.print("Enter the room number to reserve: ");
                    int roomNumber = scanner.nextInt();
                    makeReservation(roomNumber);
                    break;
                case 3:
                    System.out.println("Booking Details:");
                    BookingDetails();
                    break;
                default:
                    System.out.println("Invalid option.");
            }
            System.out.println("Welcome! Please Enter:\n\"1\" To Search For Available Rooms\n\"2\" To Make A Reservation\n\"3\" To View Booking Details\n\"4\" To Exit");
            choice = scanner.nextInt();
        }
        System.out.println("Hotel Reservation System closed as per request");
    }

    private static void initializeRooms() {
        for (int i = 0; i < roomsCount; i++) {
            roomNumbers[i] = i + 1;
            roomCategories[i] = (i < 3) ? "Standard" : "Deluxe";
            roomAvailability[i] = true;
        }
    }

    private static void AvailableRooms() {
        for (int i = 0; i < roomsCount; i++) {
            if (roomAvailability[i]) {
                System.out.println("Room " + roomNumbers[i] + " - " + roomCategories[i] + " - " +
                        (roomAvailability[i] ? "Available" : "Booked"));
            }
        }
    }

    private static void makeReservation(int roomNumber) {
        if (roomNumber >= 1 && roomNumber <= roomsCount && roomAvailability[roomNumber - 1]) {
            roomAvailability[roomNumber - 1] = false;
            System.out.println("Room " + roomNumbers[roomNumber - 1] + " (Category: " + roomCategories[roomNumber - 1] +
                    ") booked successfully.");

            if (paymentProcessing()) {
                System.out.println("Payment successful...Reservation confirmed!");
            } else {
                System.out.println("Payment failed...Reservation canceled!");
                roomAvailability[roomNumber - 1] = true;
            }
        } else {
            System.out.println("Invalid room number.");
        }
    }

    private static boolean paymentProcessing() {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Make Payment: $");
        double amount = scanner.nextDouble();

        System.out.println("Processing payment...");

        return Math.random() < 0.8;
    }

    private static void BookingDetails() {
        for (int i = 0; i < roomsCount; i++) {
            System.out.println("Room " + roomNumbers[i] + " (Category: " + roomCategories[i] + ") - " +
                    (roomAvailability[i] ? "Available" : "Booked"));
        }
    }
}
