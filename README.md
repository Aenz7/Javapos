Sure, here's a simplified example of a retail and hotel management system in Java:

```java
import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;

// Define Product class for retail management
class Product {
    private String name;
    private double price;
    private int quantity;

    public Product(String name, double price, int quantity) {
        this.name = name;
        this.price = price;
        this.quantity = quantity;
    }

    // Getters and setters
    public String getName() {
        return name;
    }

    public double getPrice() {
        return price;
    }

    public int getQuantity() {
        return quantity;
    }

    public void setQuantity(int quantity) {
        this.quantity = quantity;
    }
}

// Define Room class for hotel management
class Room {
    private int number;
    private boolean available;
    private double price;

    public Room(int number, double price) {
        this.number = number;
        this.price = price;
        this.available = true;
    }

    // Getters and setters
    public int getNumber() {
        return number;
    }

    public boolean isAvailable() {
        return available;
    }

    public void setAvailable(boolean available) {
        this.available = available;
    }

    public double getPrice() {
        return price;
    }
}

// Main class to manage retail and hotel functionalities
public class ManagementSystem {
    private List<Product> products = new ArrayList<>();
    private List<Room> rooms = new ArrayList<>();

    // Method to add a product to the inventory
    public void addProduct(String name, double price, int quantity) {
        products.add(new Product(name, price, quantity));
        System.out.println("Product '" + name + "' added successfully.");
    }

    // Method to list available products
    public void listProducts() {
        System.out.println("Available Products:");
        for (Product product : products) {
            System.out.println("Name: " + product.getName() + ", Price: " + product.getPrice() + ", Quantity: " + product.getQuantity());
        }
    }

    // Method to add a room to the hotel
    public void addRoom(int number, double price) {
        rooms.add(new Room(number, price));
        System.out.println("Room " + number + " added successfully.");
    }

    // Method to list available rooms
    public void listRooms() {
        System.out.println("Available Rooms:");
        for (Room room : rooms) {
            if (room.isAvailable()) {
                System.out.println("Room Number: " + room.getNumber() + ", Price: " + room.getPrice());
            }
        }
    }

    // Main method to run the management system
    public static void main(String[] args) {
        ManagementSystem system = new ManagementSystem();
        Scanner scanner = new Scanner(System.in);

        while (true) {
            System.out.println("\n1. Add Product");
            System.out.println("2. List Products");
            System.out.println("3. Add Room");
            System.out.println("4. List Rooms");
            System.out.println("5. Exit");

            System.out.print("Enter your choice: ");
            int choice = scanner.nextInt();

            switch (choice) {
                case 1:
                    System.out.print("Enter product name: ");
                    String productName = scanner.next();
                    System.out.print("Enter product price: ");
                    double productPrice = scanner.nextDouble();
                    System.out.print("Enter product quantity: ");
                    int productQuantity = scanner.nextInt();
                    system.addProduct(productName, productPrice, productQuantity);
                    break;
                case 2:
                    system.listProducts();
                    break;
                case 3:
                    System.out.print("Enter room number: ");
                    int roomNumber = scanner.nextInt();
                    System.out.print("Enter room price: ");
                    double roomPrice = scanner.nextDouble();
                    system.addRoom(roomNumber, roomPrice);
                    break;
                case 4:
                    system.listRooms();
                    break;
                case 5:
                    System.out.println("Exiting program.");
                    scanner.close();
                    System.exit(0);
                default:
                    System.out.println("Invalid choice. Please try again.");
            }
        }
    }
}
```

This code provides basic functionalities for adding products to the retail inventory, listing available products, adding rooms to the hotel, and listing available rooms. It uses simple console input/output for interaction. You can expand upon this codebase by adding more features such as customer management, billing, and reservation systems for both retail and hotel management.

#add car dealer showroom management system

---batch
#!/bin/bash

# Create project directory
project_name="CarDealerShowroomManagement"
mkdir $project_name
cd $project_name

# Create directory for Maven project structure
mkdir -p src/main/java/com/cardealer
mkdir -p src/main/resources
mkdir -p src/test/java/com/cardealer
mkdir -p target

# Create pom.xml file
cat <<EOL > pom.xml
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>
    <groupId>com.cardealer</groupId>
    <artifactId>CarDealerShowroomManagement</artifactId>
    <version>1.0-SNAPSHOT</version>
    
    <properties>
        <maven.compiler.source>1.8</maven.compiler.source>
        <maven.compiler.target>1.8</maven.compiler.target>
    </properties>

    <dependencies>

