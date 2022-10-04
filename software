#include <iostream>
#include <string>
#include <fstream>
#include <string.h>
#include <fstream>
#include <chrono>
#include <thread>

using namespace std;

string bookName[50] = {};
string bookId[50] = {};
string bookStock[50] = {};
string bookAuthor[50] = {};
string bookPrice[50] = {};

void addBooks(string);
void loggedin(string);
void idUpdate(string);
void bookUpdate(string);
void adminLogin(string);
void searchRecord(string);
void registration();
void login();
int main();

void goingBack()
{
    std::chrono::seconds dura(1);
    std::this_thread::sleep_for(dura);
    system("cls");
}

void save_and_exit()
{
    ofstream myFile, myFile1, myFile2, myFile3, myFile4;
    myFile.open("BookName.txt");
    myFile1.open("BookAuthor.txt");
    myFile2.open("BookStock.txt");
    myFile3.open("BookID.txt");
    myFile4.open("BookPrice.txt");

    for (int x = 0; x < 50; x++)
    {
        if (bookId[x] == "\0")
        {
            break;
        }
        else
        {
            myFile << bookName[x] << "\n";
            myFile1 << bookAuthor[x] << "\n";
            myFile2 << bookStock[x] << "\n";
            myFile3 << bookId[x] << "\n";
            myFile4 << bookPrice[x] << "\n";
        }
    }
    system("cls");
    cout << "\t++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++\n\n";
    cout << "\t                            GENIUS BOOKS \n\n";
    cout << "\t------------------------------- EXIT -----------------------------------\n\n\n";
    cout << "                                            " << endl;
    cout << "\t------------------- THANK YOU AND HAVE A GOOD DAY ! --------------------\n\n";
    cout << "\t******** Developed by Navindu Karunarathne (GM/HDCSE/CMU/04/18) ********\n\n";
    exit(0);
}

void booknameFile()
{
    string line;
    ifstream myFile("BookName.txt");
    if (myFile.is_open())
    {
        int x = 0;
        while (getline(myFile, line))
        {
            bookName[x] = line;
            x++;
        }
    }
}

void bookpriceFile()
{
    string line;
    ifstream myFile("BookPrice.txt");
    if (myFile.is_open())
    {
        int x = 0;
        while (getline(myFile, line))
        {
            bookPrice[x] = line;
            x++;
        }
    }
}

void bookauthorFile()
{
    string line;
    ifstream myFile("BookAuthor.txt");
    if (myFile.is_open())
    {
        int x = 0;
        while (getline(myFile, line))
        {
            bookAuthor[x] = line;
            x++;
        }
    }
}

void booknstockFile()
{
    string line;
    ifstream myFile("BookStock.txt");
    if (myFile.is_open())
    {
        int x = 0;
        while (getline(myFile, line))
        {
            bookStock[x] = line;
            x++;
        }
    }
}

void bookidFile()
{
    string line;
    ifstream myFile("BookID.txt");
    if (myFile.is_open())
    {
        int x = 0;
        while (getline(myFile, line))
        {
            bookId[x] = line;
            x++;
        }
    }
}

void showBooks(string isAdmin)
{
    system("cls");
    cout << "\t++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++\n\n";
    cout << "\t                            GENIUS BOOKS \n\n";
    cout << "\t-----------------------------Show Books---------------------------------\n\n\n";
    cout << "                                            " << endl;
    string bdd;
    //system("cls");
    int counter = 0;
    for (int x = 0; x < 50; x++)
    {
        if (bookId[x] != "\0")
        {
            counter++;
            cout << "\t" << counter << ".)" << endl;
            cout << "\tBook ID         : " << bookId[x] << endl;
            cout << "\tName            : " << bookName[x] << endl;
            cout << "\tPrice           : " << bookPrice[x] << "/=" << endl;
            cout << "\tAuthor          : " << bookAuthor[x] << endl;
            cout << "\tAvailable Stock : " << bookStock[x] << endl;
            cout << "\n\t========================================================\n" << endl;
        }
    }
    if (counter == 0)
    {
        cout << "\tNo record(s) found!" << endl;
        goingBack();
        if (isAdmin == "1")
        {
            adminLogin(isAdmin);
        }
        else
        {
            loggedin(isAdmin);
        }
    }
    cout << "\tEnter 0 to go back :> ";
    cin >> bdd;
    if (bdd == "0")
    {
        if (isAdmin == "1")
        {
            adminLogin(isAdmin);
        }
        else if(isAdmin == "0")
        {
            loggedin(isAdmin);
        }
    }
    else
    {
        cout << "\n\tWrong choice!";
        goingBack();
        if (isAdmin == "1")
        {
            adminLogin(isAdmin);
        }
        else
        {
            loggedin(isAdmin);
        }
    }
}

void addBooks(string isAdmin)
{
    system("cls");
    cout << "\t++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++\n\n";
    cout << "\t                            GENIUS BOOKS \n\n";
    cout << "\t----------------------------- Add Books ------------------------------\n\n\n";
    cout << "                                            " << endl;
    char yn;
    char bName[50];
    char bId[50];
    char bA[50];
    char bS[5];
    char bP[5];

    cout << "\tEnter book ID   :> ";
    cin.ignore();
    cin.getline(bId, 50);
    cout << "\tEnter book name :> ";
    cin.getline(bName, 50);
    cout << "\tEnter price     :> ";
    cin.getline(bP, 50);
    cout << "\tEnter author    :> ";
    cin.getline(bA, 50);
    cout << "\tEnter quentity  :> ";
    //cin.ignore();
    cin.getline(bS, 5);

    for (int x = 0; x < 50; x++)
    {
        if (bookId[x] == "\0")
        {
            bookId[x] = bId;
            bookName[x] = bName;
            bookStock[x] = bS;
            bookAuthor[x] = bA;
            bookPrice[x] = bP;
            break;
        }
    }
    cout << "\n" << "\tDo you want to add more books? (y/n) : ";
    cin >> yn;
    if (yn == 'y')
    {
        char yn;
        addBooks(isAdmin);
    }
    else if (yn == 'n')
    {
        char yn;
        adminLogin(isAdmin);
    }
    else
    {
        cout << "\tWrong choice!\n\tGoing back...";
        goingBack();
        adminLogin(isAdmin);
    }
}

void searchRecord(string search, string isAdmin)
{
    string yn;
    system("cls");
    int counter = 0;
    system("cls");
    cout << "\t++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++\n\n";
    cout << "\t                            GENIUS BOOKS \n\n";
    cout << "\t--------------------------- Search Books --------------------------------\n\n\n";
    cout << "                                            " << endl;
    for (int x = 0; x < 50; x++)
    {
        if (bookId[x] == search)
        {
            counter++;
            cout << "\t| " << counter << ".)" << "\n";
            cout << "\t| Book ID         : " << bookId[x] << "\n";
            cout << "\t| Name            : " << bookName[x] << "\n";
            cout << "\t| Author          : " << bookAuthor[x] << endl;
            cout << "\t| Price           : " << bookAuthor[x] << "/=" << endl;
            cout << "\t| Available Stock : " << bookStock[x] << endl;
            cout << "\t==================================================\n" << endl;
            cout << "\tEnter 0 to go back :> ";
            cin >> yn;
            if (yn == "0")
            {
                if (isAdmin == "1")
                {
                    adminLogin(isAdmin);
                }
                if (isAdmin == "0")
                {
                    loggedin(isAdmin);
                }
            }
            else
            {
                cout << "\tWrong choice!\n\tGoing back...";
                goingBack();
                bookUpdate(isAdmin);
            }
        }
    }

    if (counter == 0)
    {
        cout << "\tNo record found" << endl;
        goingBack();
        if (yn == "0")
        {
            if (isAdmin == "1")
            {
                adminLogin(isAdmin);
            }
            if (isAdmin == "0")
            {
                loggedin(isAdmin);
            }
        }
        cout << "\tEnter 0 to go back :> ";
        cin >> yn;
        if (yn == "0")
        {
            if (isAdmin == "1")
            {
                adminLogin(isAdmin);
            }
            if (isAdmin == "0")
            {
                loggedin(isAdmin);
            }
        }
        else
        {
            if (isAdmin == "1")
            {
                cout << "\tWrong choice!\n\tGoing back...";
                goingBack();
                adminLogin(isAdmin);
            }
            if (isAdmin == "0")
            {
                cout << "\tWrong choice!\n\tGoing back...";
                goingBack();
                loggedin(isAdmin);
            }
        }
    }
}

void authorUpdate(string search, string isAdmin)
{
    system("cls");
    char bA[50];
    string choice;
    cout << "\t++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++\n\n";
    cout << "\t                            GENIUS BOOKS \n\n";
    cout << "\t--------------------------- Author update ------------------------------\n\n\n";

    int counter = 0;

    for (int x = 0; x < 50; x++)
    {
        if (bookId[x] == search)
        {
            counter++;
            cout << "\tEnter new author :> ";
            cin.getline(bA, 50);
            bookAuthor[x] = bA;
            system("cls");
            cout << "\n\tSuccessfully updated" << endl;
            std::chrono::seconds dura(1);
            std::this_thread::sleep_for(dura);
            bookUpdate(isAdmin);
        }
    }
    if (counter == 0)
    {
        string bkID;
        cout << "\n\tBook ID does not exsist!\n\tTry again...";
        std::chrono::seconds dura(2);
        std::this_thread::sleep_for(dura);
        bookUpdate(isAdmin);
    }
}

void priceUpdate(string search, string isAdmin)
{
    system("cls");
    char bA[50];
    string choice;
    cout << "\t++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++\n\n";
    cout << "\t                            GENIUS BOOKS \n\n";
    cout << "\t--------------------------- Price update -------------------------------\n\n\n";

    int counter = 0;

    for (int x = 0; x < 50; x++)
    {
        if (bookId[x] == search)
        {
            counter++;
            cout << "\tEnter new price : ";
            cin.getline(bA, 50);
            bookPrice[x] = bA;
            cout << "\tSuccessfully updated\n\tGoing back..." << endl;
            goingBack();
            bookUpdate(isAdmin);
        }
    }
    if (counter == 0)
    {
        cout << "\tOperation unsucessful!!\n\tGoing back..." << endl;
        goingBack();
        bookUpdate(isAdmin);
    }
    else
    {
        cout << "\tWrong choice!\n\tGoing back...";
        goingBack();
        bookUpdate(isAdmin);
    }
}

void nameUpdate(string search, string isAdmin)
{
    system("cls");
    char bN[50];
    string choice;
    cout << "\t++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++\n\n";
    cout << "\t                            GENIUS BOOKS \n\n";
    cout << "\t---------------------------- Name update -------------------------------\n\n\n";

    int counter = 0;

    for (int x = 0; x < 50; x++)
    {
        if (bookId[x] == search)
        {
            counter++;
            cout << "\tBook name : ";
            cin.getline(bN, 50);
            bookName[x] = bN;
            system("cls");
            cout << "\n\tSuccessfully updated\n" << endl;
            std::chrono::seconds dura(2);
            std::this_thread::sleep_for(dura);
            adminLogin(isAdmin);
        }
    }
    if (counter == 0)
    {
        string c;
        cout << "\tOpertation unsuccessfull!\n\tGoing back..." << endl;
        goingBack();
        bookUpdate(isAdmin);
    }
}

void qUpdate(string search, string isAdmin)
{
    system("cls");
    char bQ[5];
    string choice;
    cout << "\t++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++\n\n";
    cout << "\t                            GENIUS BOOKS \n\n";
    cout << "\t-------------------------- Quentity update -----------------------------\n\n\n";

    int counter = 0;

    for (int x = 0; x < 50; x++)
    {
        if (bookId[x] == search)
        {
            counter++;
            cout << "\tAdd quentity : ";
            cin.getline(bQ, 50);
            bookStock[x] = bQ;
            cout << "\tSuccessfully updated" << endl;
            std::chrono::seconds dura(2);
            std::this_thread::sleep_for(dura);
        }
        if (counter == 0)
        {
            cout << "\tOperation unsuccessfull!!\n\tGoing back..." << endl;
            goingBack();
            bookUpdate(isAdmin);
        }
    }
}

void idUpdate(string search, string isAdmin)
{
    system("cls");
    cout << endl;
    char bID[5];
    string choice;
    string yn;
    cout << "\t++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++\n\n";
    cout << "\t                            GENIUS BOOKS \n\n";
    cout << "\t----------------------------- ID update --------------------------------\n\n\n";

    int counter = 0;

    for (int x = 0; x < 50; x++)
    {
        if (bookId[x] == search)
        {
            counter++;
            cout << "\tBook ID found" << endl;
            cout << "\tEnter new book ID : ";
            cin.getline(bID, 5);
            bookId[x] = bID;
            cout << "\t\nSuccessfully updated\n" << endl;
            std::chrono::seconds dura(1);
            std::this_thread::sleep_for(dura);
            system("cls");
            goingBack();
            bookUpdate(isAdmin);
        }
    }
    if (counter == 0)
    {

        cout << "\tUpdate unsucessful!!!\n\tDo you want to try again? (y/n) : ";
        cin >> yn;
        if (yn == "y")
        {
            string bID;
            cin.ignore();
            cout << "\tEnter book ID : ";
            getline(cin, bID);
            idUpdate(bID, isAdmin);
        }
        else if (yn == "n")
        {
            bookUpdate(isAdmin);
        }
        else
        {
            cout << "\tWrong choice! going back...\n" << endl;
            goingBack();
            bookUpdate(isAdmin);
        }
    }
}

void bookUpdate(string isAdmin)
{
    system("cls");
    string bID;
    int choice;
    cout << "\t++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++\n\n";
    cout << "\t                            GENIUS BOOKS \n\n";
    cout << "\t--------------------------- Update Books --------------------------------\n\n\n";
    cout << "\t| 1.Update book name      |" << endl;
    cout << "\t| 2.Update book author    |" << endl;
    cout << "\t| 3.Update book price     |" << endl;
    cout << "\t| 4.Update book quantity  |" << endl;
    cout << "\t| 5.Update book ID        |" << endl;
    cout << "\t| 0.Go back               |" << endl;

    cout << "\n\tEnter your choice :> ";
    cin >> choice;

    switch (choice)
    {
    case 1:
    {
        cin.ignore();
        cout << "\tEnter book ID : ";
        getline(cin, bID);
        nameUpdate(bID, isAdmin);
        break;
    }
    case 2:
    {
        cin.ignore();
        cout << "\tEnter book ID : ";
        getline(cin, bID);
        authorUpdate(bID, isAdmin);
        break;
    }
    case 3:
        cin.ignore();
        cout << "\tEnter book ID : ";
        getline(cin, bID);
        priceUpdate(bID, isAdmin);
        break;
    case 4:
    {
        cin.ignore();
        cout << "\tEnter book ID : ";
        getline(cin, bID);
        qUpdate(bID, isAdmin);
        break;
    }
    case 5:
    {
        cin.ignore();
        cout << "\tEnter book ID : ";
        getline(cin, bID);
        idUpdate(bID, isAdmin);
        break;
    }
    case 0:
        adminLogin(isAdmin);
        break;
    default:
        cout << "\tWrong choice! Try again.." << endl;
        bookUpdate(isAdmin);
    }
}

void deleteBook(string isAdmin)
{
    system("cls");
    char bID[5];
    string choice;
    string yn;
    string search;

    cout << "\t++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++\n\n";
    cout << "\t                            GENIUS BOOKS \n\n";
    cout << "\t--------------------------- Delete Books ------------------------------\n\n";

    cout << "\tEnter ID to delete :> ";
    cin >> search;

    int counter = 0;

    for (int x = 0; x < 50; x++)
    {
        if (bookId[x] == search)
        {
            cout << "\tAre you sure to detele the item (y/n) :> ";
            cin >> yn;
            cout << endl;
            if (yn == "y")
            {
                string yn;
                counter++;
                bookId[x] = "";
                bookAuthor[x] = "";
                bookName[x] = "";
                bookStock[x] = "";
                bookPrice[x] = "";
                cout << "\tSuccessfully deleted\n" << endl;
                cout << "\tEnter 0 to go back :> ";
                cin >> yn;
                if (yn == "0")
                {
                    string yn;
                    system("cls");
                    adminLogin(isAdmin);
                }
            }
            else if (yn == "n")
            {
                string yn;
                adminLogin(isAdmin);
            }
            else
            {
                cout << "\tWrong choice!\n\tGoing back...";
                goingBack();
                adminLogin(isAdmin);
            }
        }
    }
    if (counter == 0)
    {
        cout << "\tUpdate unsucessful!!!\n\tDo you want to try again? (y/n) : ";
        cin >> yn;
        if (yn == "y")
        {
            deleteBook(isAdmin);
        }
        else if (yn == "n")
        {
            adminLogin(isAdmin);
        }
        else
        {
            cout << "\t Wrong choice";
            adminLogin(isAdmin);
        }
    }
}

void adminLogin(string isAdmin)
{
    system("cls");
    cout << "\t++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++\n\n";
    cout << "\t                            GENIUS BOOKS \n\n";
    cout << "\t------------------------------- MENU -----------------------------------\n\n\n";
    string bookID;
    int option;
    cout << "\t| 1. Add books       |" << endl;
    cout << "\t| 2. Update books    |" << endl;
    cout << "\t| 3. Search books    |" << endl;
    cout << "\t| 4. Show books      |" << endl;
    cout << "\t| 5. Delete books    |" << endl;
    cout << "\t| 6. Logout          |" << endl;
    cout << "\t| 0. Save and exit   |" << endl;

    cout << "\n\tEnter your choice :> ";
    cin >> option;

    switch (option)
    {
    case 1:
        addBooks(isAdmin);
        break;
    case 2:
        bookUpdate(isAdmin);
        break;
    case 3:
        cout << "\tEnter book ID to continue :> ";
        cin.ignore();
        getline(cin, bookID);
        searchRecord(bookID, isAdmin);
        break;
    case 4:
        showBooks(isAdmin);
        break;
    case 5:
        deleteBook(isAdmin);
        break;
    case 6:
        system("cls");
        cout << "\n\tLogging you out";
        std::chrono::seconds dura(2);
        std::this_thread::sleep_for(dura);
        main();
        break;
    case 0:
        save_and_exit();
        break;
    default:
        cout << "\n\tWrong choice!\n\tTry again..." << endl;
        std::this_thread::sleep_for(dura);
        loggedin(isAdmin);
        break;
    }
}

void loggedin(string isAdmin)
{
    system("cls");
    cout << "\t++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++\n\n";
    cout << "\t                            GENIUS BOOKS \n\n";
    cout << "\t------------------------------- MENU -----------------------------------\n\n\n";
    string bookID;
    int option;
    cout << "\t| 1. Search books    |" << endl;
    cout << "\t| 2. Show books      |" << endl;
    cout << "\t| 3. Logout          |" << endl;
    cout << "\t| 0. Exit            |" << endl;

    cout << "\n\tEnter your choice :> ";
    cin >> option;

    switch (option)
    {
    case 1:
        cout << "\n\tEnter book ID to continue :> ";
        cin.ignore();
        getline(cin, bookID);
        searchRecord(bookID, isAdmin);
        break;
    case 2:
        showBooks(isAdmin);
        break;
    case 3:
        main();
        break;
    case 0:
        system("cls");
        cout << "\t++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++\n\n";
        cout << "\t                            GENIUS BOOKS \n\n";
        cout << "\t------------------------------- EXIT -----------------------------------\n\n\n";
        cout << "                                            " << endl;
        cout << "\t------------------- THANK YOU AND HAVE A GOOD DAY ! --------------------\n\n";
        cout << "\t******** Developed by Navindu Karunarathne (GM/HDCSE/CMU/04/18) ********\n\n";
        exit(0);
    default:
        cout << "\n\tWrong choice!\n\tTry again..." << endl;
        std::chrono::seconds dura(1);
        std::this_thread::sleep_for(dura);
        loggedin(isAdmin);
        break;
    }
}

void login()
{
    int count = 0;
    string userID, password, id, pass;
    system("cls"); //Clears the screen
    cout << "\t++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++\n\n";
    cout << "\t                            GENIUS BOOKS \n\n";
    cout << "\t------------------------------- LOGIN ----------------------------------\n\n\n";
    cout << "                                            " << endl;
    cout << "\tEnter the Username and Password to login \n " << endl;
    cout << "\tUsername :> ";
    cin >> userID;
    cout << "\tPassword :> ";
    cin >> password;

    ifstream input("login.txt");
    while (input >> id >> pass)
    {
        if ((userID == "admin") && (password == "admin"))
        {
            system("cls");
            count = 1;
            string isAdmin = "1";
            adminLogin(isAdmin);
        }
        if ((id == userID) && (pass == password))
        {
            system("cls");
            count = 1;
            string isAdmin = "0";
            loggedin(isAdmin);
        }
    }
    input.close();

    if (count != 1)
    {
        char newUser = '0';
        system("cls");
        cout << "\t++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++\n\n";
        cout << "\t                            GENIUS BOOKS \n\n";
        cout << "\t------------------------------- LOGIN ----------------------------------\n\n\n";
        cout << "\n\tIncorrect Username or Password !" << endl;
        cout << "\n\tDo you want to register a new user (y/n) :> ";
        cin >> newUser;
        if (newUser == 'y')
        {
            system("cls");
            registration();
        }
        else if (newUser == 'n')
        {
            cout << "\n\tTry again...";
            std::chrono::seconds dura(1);
            std::this_thread::sleep_for(dura);
            login();
        }
        else
        {
            cout << "\tWrong choice!\n\tTry to login again...";
            std::chrono::seconds dura(1);
            std::this_thread::sleep_for(dura);
            login();
        }
    }
}

void registration()
{
    char islogin = '0';
    string newID, ruserID, rPassword1, rPassword, rID, rPass;
    system("cls");
    cout << "\t++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++\n\n";
    cout << "\t                            GENIUS BOOKS \n\n";
    cout << "\t-------------------------- Create new user -----------------------------\n\n";
    cout << "\n\tEnter Username :> ";
    cin >> ruserID;

    ifstream input("login.txt");
    while (input >> newID)
    {
        if (newID == ruserID)
        {
            cout << "\n\tUser already exists, do you want to login (y/n) :> ";
            cin >> islogin;
            if (islogin == 'y')
            {
                system("cls");
                login();
            }
            else
            {
                system("cls");
                registration();
            }
        }
    }

    cout << endl;
    cout << "\tEnter Password :> ";
    cin >> rPassword1;
    cout << "\tRe-enter Password :> ";
    cin >> rPassword;

    if (rPassword == rPassword1)
    {
        ofstream f1("login.txt", ios::app); //append to the end
        f1 << ruserID << ' ' << rPassword << endl;
        system("cls");
        cout << "\n\tRegistration sucessful ! \n";
        std::chrono::seconds dura(1);
        std::this_thread::sleep_for(dura);
        system("cls");
        main();
    }

    else
    {
        system("cls");
        cout << "\n\tPassword does not match, please try again... ";
        std::chrono::seconds dura(1);
        std::this_thread::sleep_for(dura);
        registration();
    }
}

int main()
{
    int c;
    booknameFile();
    bookauthorFile();
    booknstockFile();
    bookidFile();
    bookpriceFile();
    while (true)
    {
        char n = 0;
        cout << "\t++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++\n\n";
        cout << "\t                            GENIUS BOOKS \n\n";
        cout << "\t------------------------------------------------------------------------\n\n\n";
        cout << "                                            " << endl;
        cout << "\t| Enter 1 to LOGIN           |" << endl;
        cout << "\t| Enter 2 to REGISTER        |" << endl;
        cout << "\t| Enter 0 to EXIT            |" << endl;
        cout << "\n\tEnter your choice :> ";
        cin >> c;
        if (!cin)
        {
            cin.clear();
            cin.ignore(numeric_limits<streamsize>::max(), '\n');
            cout << "Wrong Choice. Enter 1 or 2 or 0 " << endl;
            std::chrono::seconds dura(1);
            std::this_thread::sleep_for(dura);
            system("cls");
            continue;
        }
        else
        {
            switch (c)
            {
            case 1:
                login();
                break;

            case 2:
                registration();
                break;

            case 0:
                save_and_exit();

            default:
                cout << "Wrong Choice. Enter 1 or 2 or 0 " << endl;
                std::chrono::seconds dura(1);
                std::this_thread::sleep_for(dura);
                system("cls");
                main();
            }
        }
        break;
    }
    return 0;
}
