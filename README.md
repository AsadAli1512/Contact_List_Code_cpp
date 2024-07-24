# Contact_List_Code_cpp
Author: Asad Ali
<br>
Here is the simple code in c++, which has functions to handle Contact List such as  to add update contact, to search contact and to delete the contact.
<br>


#include<iostream>
#include<string>
#include<string.h>
using namespace std;
class contact
{
private:
	string name;
	string num;
	string email;
	string company;
public:

	contact() {
		
			name = "Null";
			num = "Null";
			email = "Null";
			company = "Null";
			
	          }
	void set_data()
	{

		cout << "\nEnter Name : ";
		cin >> name;
		cout << "\nEnter Phone Number : ";
		cin >> num;
		cout << "\nEnter Email : ";
		cin >> email;
		cout << "\nEnter Company : ";
		cin >> company;
		cout << "\n\t\t**********" << endl;
		
	}
	
	string get_name()
	{
		return name;
	}
	string get_num()
	{
		return num;
	}string get_email()
	{
		return email;
	}
	string get_company()
	{
		return company;
	}

	void record()
	{
		cout << "Name : " << get_name() << endl;
		cout << "Phone Num : " << get_num() << endl;
		cout << "Email : " << get_email() << endl;
		cout << "Company : " << get_company() << endl;
		cout << "\t\t**********" << endl;

	}
	
};




int main()
{
	cout << "\n\t\tHello in Contact list : " << endl;
	cout << "Enter size of contact list " << endl;
	cout << "  Size : ";
	int size;
	cin >> size;
	contact* arr = new contact[size];
	for (int i = 0; i < size; i++)
	{
		arr[i].set_data();
	}

	cout << "\n\n\t\tMenu List : " << endl;
	int select = 0;
	cout << "1.Serach Contact " << endl;
	cout << "2.For update Contact" << endl;
	cout << "3.Print All Contact List Record " << endl;
	cout << "Choose : ";	
	cin >> select;
	switch (select) //outer swutch
	{
	case 1:
	{
		int s = 0;
		cout << "\nAlright! Which way you want to serach :" << endl;
		cout << "1.By Name " << endl;
		cout << "2.By Phone Number " << endl;
		cout << "3.By Email " << endl;
		cout << "4.By Company " << endl;
		cout << "Choose : ";
		cin >> s;
		string input;
		int index = -2;

		switch (s) //inner switch
		{
		case 1: //inner case
		{
			cout << "\nEnter Searcher Contact Name : ";
			cin >> input;
			for (int i = 0; i < size; i++)
			{
				if (arr[i].get_name() == input)
				{
					index = i;
					break;
				}
			}
			if (index == -2)
			{
				cout << "\nNO Data Found!" << endl;
			}
			else
			{
				arr[index].record();
			}
		}
		break;

		case 2: //inner case
		{
			cout << "\nEnter Searcher Contact Phone Number : ";
			cin >> input;
			for (int i = 0; i < size; i++)
			{
				if (arr[i].get_num() == input)
				{
					index = i;
					break;
				}
			}
			if (index == -2)
			{
				cout << "\nNO Data Found!" << endl;
			}
			else
			{
				arr[index].record();
			}
		}
		break;


		case 3: //inner case
		{
			cout << "\nEnter Searcher Contact Email : ";
			cin >> input;
			for (int i = 0; i < size; i++)
			{
				if (arr[i].get_email() == input)
				{
					index = i;
					break;
				}
			}
			if (index == -2)
			{
				cout << "\nNO Data Found!" << endl;
			}
			else
			{
				arr[index].record();
			}
		}
		break;


		case 4: //inner case
		{
			cout << "\nEnter Searcher Contact Company : ";
			cin >> input;
			for (int i = 0; i < size; i++)
			{
				if (arr[i].get_company() == input)
				{
					index = i;
					break;
				}
			}
			if (index == -2)
			{
				cout << "\nNO Data Found!" << endl;
			}
			else
			{
				arr[index].record();
			}
		}
		break;

		default:
		{
			cout << "\nInvalid input!" << endl;
		}
		}
	}
		break;

	case 2://Outer loop
	{
		string update;
		int index = -2;
		cout << "\n\nWhich Conatnt do you want to update : " << endl;
		cout << "Enter it's Name or Phone Number or Email or Company" << endl;
		cin >> update;
		for (int i = 0; i < size; i++)
		{
			if (arr[i].get_name() == update || arr[i].get_num() == update || arr[i].get_email() == update || arr[i].get_company() == update)
			{
				index = i;
				break;
			}
		}
		if (index == -2)
		{
			cout << "\nRecord Not Found!" << endl;
		}
		else
		{
			cout << "\n Update it : ";
			arr[index].set_data();
		}
	}
	break;

	case 3:
	{
		cout << "\n\n\n   All Contact Record list : " << endl;
		for (int i = 0; i < size; i++)
		{
			arr[i].record();
		}

	}
	break;
	default:
		cout << "\nInvalid Input!" << endl;
}


}

