#include <iostream>
#include <string>
#define MAX_ROOMS 100
#define MAX_GUESTS 100

using namespace std;

struct Guest {
    int id;
    string name;
    int age;
    string address;
    string phoneNumber;
};

struct Room {
    int roomNumber;
    bool isBooked;
    Guest* guest;
    string host;
    string startTime;
    string endTime;
    int chairsAvailable;
};

class Hotel {
    Room rooms[MAX_ROOMS];
    Guest guests[MAX_GUESTS];
    int guestCount;
    int roomCount;

public:
    Hotel(int numRooms) : roomCount(numRooms), guestCount(0) {
        for (int i = 0; i < numRooms; ++i) {
            rooms[i].roomNumber = i + 1;
            rooms[i].isBooked = false;
            rooms[i].guest = nullptr;
            rooms[i].chairsAvailable = 0;
        }
    }

    void addGuest(int id, string name, int age, string address, string phoneNumber) {
        if (guestCount < MAX_GUESTS) {
            guests[guestCount].id = id;
            guests[guestCount].name = name;
            guests[guestCount].age = age;
            guests[guestCount].address = address;
            guests[guestCount].phoneNumber = phoneNumber;
            guestCount++;
        } else {
            cout << "Guest list is full." << endl;
        }
    }

    void bookRoom(int guestID, int roomNumber, string host, string startTime, string endTime, int chairs) {
        for (int i = 0; i < roomCount; ++i) {
            if (rooms[i].roomNumber == roomNumber && !rooms[i].isBooked) {
                rooms[i].isBooked = true;
                for (int j = 0; j < guestCount; ++j) {
                    if (guests[j].id == guestID) {
                        rooms[i].guest = &guests[j];
                        rooms[i].host = host;
                        rooms[i].startTime = startTime;
                        rooms[i].endTime = endTime;
                        rooms[i].chairsAvailable = chairs;
                        cout << "Room " << roomNumber << " booked by " << guests[j].name << " as host " << host << endl;
                        return;
                    }
                }
                cout << "Guest ID not found." << endl;
                return;
            }
        }
        cout << "Room not available." << endl;
    }

    void checkOut(int roomNumber) {
        for (int i = 0; i < roomCount; ++i) {
            if (rooms[i].roomNumber == roomNumber && rooms[i].isBooked) {
                rooms[i].isBooked = false;
                cout << "Room " << roomNumber << " checked out by " << rooms[i].guest->name << endl;
                rooms[i].guest = nullptr;
                rooms[i].host = "";
                rooms[i].startTime = "";
                rooms[i].endTime = "";
                rooms[i].chairsAvailable = 0;
                return;
            }
        }
        cout << "Room not found or already vacant." << endl;
    }

    void displayAvailableRooms() {
        for (int i = 0; i < roomCount; ++i) {
            if (!rooms[i].isBooked) {
                cout << "Room " << rooms[i].roomNumber << " is available." << endl;
            }
        }
    }

    void displayRoomInfo(int roomNumber) {
        for (int i = 0; i < roomCount; ++i) {
            if (rooms[i].roomNumber == roomNumber) {
                cout << "Room Number: " << rooms[i].roomNumber << endl;
                if (rooms[i].isBooked) {
                    cout << "Booked by: " << rooms[i].guest->name << endl;
                    cout << "Host: " << rooms[i].host << endl;
                    cout << "Start Time: " << rooms[i].startTime << endl;
                    cout << "End Time: " << rooms[i].endTime << endl;
                    cout << "Chairs Available: " << rooms[i].chairsAvailable << endl;
                } else {
                    cout << "Room is available." << endl;
                }
                return;
            }
        }
        cout << "Room not found." << endl;
    }
};

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
