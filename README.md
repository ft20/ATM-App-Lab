# ATM-App-Lab
This is my code for the ATM application
#include<iostream>
#include<cstdlib>
#include<windows.h>

using namespace std;

class ATM
{
	private:
		int code;
		int money;
	
	public:
		int accountno;
		int moneyview(void);
		void enter_code_money(int Code,int money);
		int entercode(int Code);
		void withdraw(int money);
		void paybills(int money);
		void transfer(int Accountno,int money);
		void query(int Code,int money);
};

int ATM::moneyview()
{
	return money;
}

void ATM::paybills(int money)
{
	cout<<endl<<"The amount you entered is being deducted for payment. Please wait!"<<endl;
	Sleep(2000);
	cout<<"Success! Your bills have been paid"<<endl<<"The remaining balance amount in your account is:"<<money-money<<endl<<endl;
}

void ATM::query(int Code,int money)
{
	cout<<endl<<"The money present in your account ("<<code<<")is "<<money<<endl;
	cout<<"You transferred amount"<<money<<" to account no "<<Code<<endl<<endl;
}

void ATM::enter_code_money(int Code,int money)
{
	code=Code;
	money=money;
}

int ATM::entercode(int Code)
{
	if(Code==code)
	{
		cout<<"Correct code verified. Correct code was entered"<<endl<<endl;
		return 1;
	}
	else
	{
		cout<<"You entered the Incorrect code"<<endl<<endl;
		return 0;
	}
}

void ATM::transfer(int Accountno,int money)
{
	cout<<"The amount you entered is being transferred to account no "<<Accountno<<"Please wait\n"<<endl<<endl;
	Sleep(2000);
	money=money-money;
}

void ATM::withdraw(int money)
{
	cout<<"The amount is being transferred to your account"<<endl;
	Sleep(2000);
	cout<<"The amount has been transferred to your account"<<endl<<"Your amount is "<<money<<endl<<"Remaining balance: "<<money-money<<endl<<endl;
	money=money-money;
}

int main(void)
{
	ATM me1,me;
	int accountno,money;
	while(1)
	{
		int choice;
		cout<<"Welcome to your ATM Application"<<endl;
		cout<<"Please select an option to continue"<<endl;
		cout<<"Please press 1 to withdraw your money"<<endl;
		cout<<"Please press 2 to transfer money using your account no."<<endl;
		cout<<"Please press 3 to pay your bills"<<endl;
		cout<<"Please press 4 to take your card out"<<endl;
		cin>>choice;
		if(choice==1&&me1.moneyview()!=0&&me1.moneyview()>0)
		{
			while(1)
			{
				cout<<endl<<"Please enter the code(to withdraw money, please enter same code as you entered earlier):";
				cin>>accountno;
				int correct=me1.entercode(accountno);
				if(correct==1)
				{
					int money;
					cout<<endl<<"Please enter the amount of money to be withdrawn:";
					cin>>money;
					me1.withdraw(money);
					break;
				}
				else
				{
					continue;
				}
			}
		}
		else
		{
			cout<<endl<<"The amount you entered is not present/sufficient in your account"<<endl;
		}
		if(choice==2&&me1.moneyview()!=0&&me1.moneyview()>0)
		{
			cout<<endl<<"Please enter the account number of the person you want to transfer the amount to(please enter eight digits only):";
			cin>>me.accountno;
			cout<<"Please enter the amount to be transferred:";
			int transferamount;
			cin>>transferamount;
			me.enter_code_money(accountno,transferamount);
			me1.transfer(me.accountno,transferamount);
			me1.query(me.accountno,transferamount);
		}
		else
		{
			cout<<endl<<"The amount you entered is not present/sufficient in your account"<<endl;
		}
		if(choice==3&&me1.moneyview()!=0&&me1.moneyview()>0)
		{
			int money;
			cout<<endl<<"Please enter the amount of your bill (please enter the sum of all bills without spaces):";
			cin>>money;
			me1.paybills(money);
		}
		else
		{
			cout<<endl<<"The amount you entered is not present/sufficient in your account"<<endl<<endl;
		}
		if(choice==4)
		{
			cout<<endl<<"Thank you for using this ATM App. Please come again"<<endl;
			cout<<endl<<"Don't forget to take your card!!!"<<endl;
			break;
		}
	}
}
