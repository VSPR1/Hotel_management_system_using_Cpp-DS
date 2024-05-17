🏨 Hotel Management System in C++ 🛠️
Welcome to the Hotel Management System repository! This project demonstrates a simple yet functional hotel management system implemented in C++. It includes features like booking rooms, checking out, and displaying available rooms, with additional scheduling capabilities.

✨ Features
Add Guest: Add guest details including name, age, address, and phone number.
Book Room: Book a room for a guest with additional scheduling features:
Set the host
Set the start time
Set the end time
Set the number of chairs available
Define the room number
Check Out: Check out a guest and make the room available for new bookings.
Display Available Rooms: View all available rooms.
Display Room Info: View detailed information about a specific room.
🚀 Getting Started
Prerequisites
A C++ compiler (e.g., g++, clang++)
A development environment (e.g., Visual Studio Code, CLion)
Installation
Clone the repository:


Copy code
git clone https://github.com/yourusername/hotel-management-system.git
cd hotel-management-system
Compile the code:


Copy code
g++ -o hotel_management_system main.cpp
Run the program:


Copy code
./hotel_management_system
Usage
Here's a quick guide on how to use the system:

Add Guests:

You can add guest details such as name, age, address, and phone number.
Book Rooms:

Book a room for a guest by specifying their ID, room number, host name, start time, end time, and the number of chairs available.
Check Out:

Check out a guest to make the room available for new bookings.
Display Available Rooms:

List all rooms that are currently available for booking.
Display Room Info:

Get detailed information about a specific room, including booking status and schedule.
📝 Example
Here's a sample usage of the program in the main function:

cpp
Copy code
int main() {
    Hotel hotel(10); // Initialize hotel with 10 rooms

    hotel.addGuest(1, "John Doe", 30, "123 Main St", "555-1234");
    hotel.addGuest(2, "Jane Smith", 25, "456 Oak St", "555-5678");

    hotel.bookRoom(1, 3, "John Doe", "10:00 AM", "12:00 PM", 20);
    hotel.bookRoom(2, 5, "Jane Smith", "2:00 PM", "4:00 PM", 15);

    cout << "Available rooms:" << endl;
    hotel.displayAvailableRooms();

    cout << "Room 3 info:" << endl;
    hotel.displayRoomInfo(3);

    hotel.checkOut(3);

    cout << "Available rooms after checkout:" << endl;
    hotel.displayAvailableRooms();

    return 0;
}
📂 File Structure
main.cpp: Contains the main code for the hotel management system.
👥 Contributing
We welcome contributions to enhance the features and capabilities of this project! Please feel free to submit pull requests or open issues.

📜 License
This project is licensed under the MIT License. See the LICENSE file for details.

💬 Contact
If you have any questions or suggestions, please feel free to reach out!

Enjoy managing your hotel with ease! 🏨✨
