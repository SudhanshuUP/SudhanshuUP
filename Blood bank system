#include <iostream>
#include <string>

using namespace std;

class BloodDonor {
public:
    string name;
    string bloodGroup;
    int age;
    string email;
    string lastDonationDate;
    string mobileNumber;

    // Default constructor
    BloodDonor() {
        name = "";
        bloodGroup = "";
        age = 0;
        email = "";
        lastDonationDate = "";
        mobileNumber = "";
    }

    BloodDonor(string n, string bg, int a, string e, string ldd, string mob) {
        name = n;
        bloodGroup = bg;
        age = a;
        email = e;
        lastDonationDate = ldd;
        mobileNumber = mob;
    }

    void displayInfo() {
        cout << "Name: " << name << endl;
        cout << "Blood Group: " << bloodGroup << endl;
        cout << "Age: " << age << endl;
        cout << "Email: " << email << endl;
        cout << "Last Donation Date: " << lastDonationDate << endl;
        cout << "Mobile Number: " << mobileNumber << endl;
    }
};

class BloodReceiver {
public:
    string name;
    string bloodGroup;
    int age;
    string email;
    string mobileNumber;

    // Default constructor
    BloodReceiver() {
        name = "";
        bloodGroup = "";
        age = 0;
        email = "";
        mobileNumber = "";
    }

    BloodReceiver(string n, string bg, int a, string e, string mob) {
        name = n;
        bloodGroup = bg;
        age = a;
        email = e;
        mobileNumber = mob;
    }

    void displayInfo() {
        cout << "Name: " << name << endl;
        cout << "Blood Group: " << bloodGroup << endl;
        cout << "Age: " << age << endl;
        cout << "Email: " << email << endl;
        cout << "Mobile Number: " << mobileNumber << endl;
    }
};
class BloodBank {
private:
    BloodDonor donors[100]; // Maximum of 100 donors
    BloodReceiver receivers[100]; // Maximum of 100 receivers
    int donorCount;
    int receiverCount;

public:
    BloodBank() {
        donorCount = 0;
        receiverCount = 0;
    }

    void addDonor(string name, string bloodGroup, int age, string email, string lastDonationDate, string mobileNumber) {
        if (donorCount < 100) {
            donors[donorCount] = BloodDonor(name, bloodGroup, age, email, lastDonationDate, mobileNumber);
            donorCount++;
            cout << "Donor added successfully!" << endl;
        } else {
            cout << "Blood donor list is full. Cannot add more donors." << endl;
        }
    }

    void addReceiver(string name, string bloodGroup, int age, string email, string mobileNumber) {
        if (receiverCount < 100) {
            receivers[receiverCount] = BloodReceiver(name, bloodGroup, age, email, mobileNumber);
            receiverCount++;
            cout << "Receiver added successfully!" << endl;
        } else {
            cout << "Blood receiver list is full. Cannot add more receivers." << endl;
        }
    }

    void displayDonors() {
        if (donorCount == 0) {
            cout << "No donors available in the blood bank." << endl;
        } else {
            cout << "List of Donors:" << endl;
            for (int i = 0; i < donorCount; i++) {
                donors[i].displayInfo();
                cout << "------------------------" << endl;
            }
        }
    }

    void displayReceivers() {
        if (receiverCount == 0) {
            cout << "No receivers available in the blood bank." << endl;
        } else {
            cout << "List of Receivers:" << endl;
            for (int i = 0; i < receiverCount; i++) {
                receivers[i].displayInfo();
                cout << "------------------------" << endl;

                // Check if the blood group is O+ or O-
                if (receivers[i].bloodGroup == "O+" || receivers[i].bloodGroup == "O-") {
                    cout << "Special Message: ";
                    cout << "I wish you a happy and healthy day! Your blood is a universal donor, which means you can save lives. Thank you for being so selfless." << endl;
                }
            }
        }
    }
};

// ...

int main() {
    BloodBank bloodBank;
    int choice;

    do {
        cout << "Blood Bank Management System" << endl;
        cout << "1. Add Donor" << endl;
        cout << "2. Add Receiver" << endl;
        cout << "3. Display Donors" << endl;
        cout << "4. Display Receivers" << endl;
        cout << "5. Exit" << endl;
        cout << "Enter your choice: ";
        cin >> choice;

        switch (choice) {
            case 1:
                {
                    string name, bloodGroup, email, lastDonationDate, mobileNumber;
                    int age;
                    cout << "Enter donor name: ";
                    cin.ignore();
                    getline(cin, name);
                    cout << "Enter donor blood group: ";
                    cin >> bloodGroup;
                    cout << "Enter donor age: ";
                    cin >> age;
                    cout << "Enter donor email: ";
                    cin.ignore();
                    getline(cin, email);
                    cout << "Enter last donation date (dd/mm/yyyy): ";
                    cin >> lastDonationDate;
                    cout << "Enter donor mobile number: ";
                    cin >> mobileNumber;
                    bloodBank.addDonor(name, bloodGroup, age, email, lastDonationDate, mobileNumber);
                }
                break;

            case 2:
                {
                    string name, bloodGroup, email, mobileNumber;
                    int age;
                    cout << "Enter receiver name: ";
                    cin.ignore();
                    getline(cin, name);
                    cout << "Enter receiver blood group: ";
                    cin >> bloodGroup;
                    cout << "Enter receiver age: ";
                    cin >> age;
                    cout << "Enter receiver email: ";
                    cin.ignore();
                    getline(cin, email);
                    cout << "Enter receiver mobile number: ";
                    cin >> mobileNumber;
                    bloodBank.addReceiver(name, bloodGroup, age, email, mobileNumber);
                }
                break;

            case 3:
                bloodBank.displayDonors();
                break;

            case 4:
                bloodBank.displayReceivers();
                break;

            case 5:
                cout << "Exiting program." << endl;
                break;

            default:
                cout << "Invalid choice. Please try again." << endl;
        }
    } while (choice != 5);

    return 0;
}
