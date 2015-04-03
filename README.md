# Operating-System-Simulator
This was done my operation systems class/


#include <iostream>
#include <cstdlib>
#include <iomanip>

using namespace std;

int main()
{
	char job0[9001], job1[9001], job2[9001], job3[9001]; //jobs name 
	int pri0, pri1, pri2, pri3; //jobs priority
	int startpage0, startpage1, startpage2, startpage3, endpage0, endpage1, endpage2, endpage3; //# of pages needed
	int ttr0, ttr1, ttr2, ttr3; //time needed to run
	int hpri0, hpri1, highestpri; //highest priority
	bool pri0BIG = false;
	bool pri1BIG = false;
	bool pri2BIG = false;
	bool pri3BIG = false;
	int bill;

	//job 0
	cout << "Please enter job zero's name" << endl;
	cin >> job0; cout << endl;
	do
	{
		cout << "Please enter job zero's priority on a scale of 1-5 \n";
		cin >> pri0; cout << endl;
	} while (pri0 < 1 || pri0 > 5);
	cout << "Please enter the first page that job zero needs\n";
	cin >> startpage0; cout << endl;
	do
	{
		cout << "Please enter the last page that job zero needs\n";
		cin >> endpage0; cout << endl;
	} while (startpage0 > endpage0);
	cout << "Please enter job zero's run time\n";
	cin >> ttr0; cout << endl;

	//job 1
	cout << "Please enter job one's name \n";
	cin >> job1; cout << endl;
	do
	{
		cout << "Please enter job one's priority on a scale of 1-5 \n";
		cin >> pri1; cout << endl;
	} while (pri1 < 1 || pri1 > 5);
	cout << "Please enter the first page that job one needs\n";
	cin >> startpage1; cout << endl;
	do
	{
		cout << "Please enter the last page that job one needs\n";
		cin >> endpage1; cout << endl;
	} while (startpage1 > endpage1);
	cout << "Please enter job one's run time \n";
	cin >> ttr1; cout << endl;

	//job 2
	cout << "Please enter job two's name \n";
	cin >> job2; cout << endl;
	do
	{
		cout << "Please enter job two's priority on a scale of 1-5 \n";
		cin >> pri2; cout << endl;
	} while (pri2 < 1 || pri2 > 5);
	cout << "Please enter the first page that job two needs\n";
	cin >> startpage2; cout << endl;
	do
	{
		cout << "Please enter the last page that job two needs\n";
		cin >> endpage2; cout << endl;
	} while (startpage2 > endpage2);
	cout << "Please enter job two's run time \n";
	cin >> ttr2; cout << endl;

	//job 3
	cout << "Please enter job three's name \n";
	cin >> job3; cout << endl;
	do
	{
		cout << "Please enter job three's priority on a scale of 1-5 \n";
		cin >> pri3; cout << endl;
	} while (pri3 < 1 || pri3 > 5);
	cout << "Please enter the first page that job three needs\n";
	cin >> startpage3; cout << endl;
	do
	{
		cout << "Please enter the last page that job three needs\n";
		cin >> endpage3; cout << endl;
	} while (startpage3 > endpage3);
	cout << "Please enter job three's run time \n";
	cin >> ttr3; cout << endl;

	//higher of 0 and 1
	if (pri0 < pri1)
	{
		hpri0 = pri1;
		pri1BIG = true;
		
	}
	else if (pri0 > pri1)
	{
		hpri0 = pri0;
		pri0BIG = true;
	}
	else if (pri0 == pri1)
	{
		hpri0 = pri0;
		pri0BIG = true;
	}

	//higher of 2 or 3 
	if (pri2 < pri3)
	{
		hpri1 = pri3;
		pri3BIG = true;
	}
	else if (pri2 > pri3)
	{
		hpri1 = pri2;
		pri2BIG = true;
	}
	else if (pri2 == pri3)
	{
		hpri1 = pri2;
		pri2BIG = true;
	}

	//highest priority
	if (hpri0 > hpri1)
	{
		if (pri0BIG == true)
		{
			cout << "Job 0 has highest priority\n";
			highestpri = hpri0;
			pri2BIG = false;
			pri3BIG = false;
		}
		else if (pri1BIG == true)
		{
			cout << "Job 1 has highest priority\n";
			highestpri = hpri0;
			pri2BIG = false;
			pri3BIG = false;
		}
	}
	else if (hpri0 < hpri1)
	{
		if (pri2BIG == true)
		{
			cout << "Job 2 has highest priority\n";
			highestpri = hpri1;
			pri0BIG = false;
			pri1BIG = false;
		}
		else if (pri3BIG == true)
		{
			cout << "Job 3 has highest priority\n";
			highestpri = hpri1;
			pri0BIG = false;
			pri1BIG = false;
		}
	}                
	else if (hpri0 == hpri1)
	{
		if (pri0BIG == true)
		{
			cout << "Job 0 goes first\n";
			highestpri = hpri0;
		}
		else if (pri1BIG == true)
		{
			cout << "Job 1 goes first\n";
			highestpri = hpri0;
		}
		
	}


	if (pri0BIG)
	{
		for (int i = (ttr0 + ttr1 + ttr2 + ttr3 + 5); i > 0; i--)
		{
			ttr0--;
			if (ttr0 == 0)
			{
				cout << "Job zero has finished \n";
				cout << "And used page " << startpage0 << " to page " << endpage0<< endl; //Autobots roll out
			}
			ttr1--;
			if (ttr1 == 0)
			{
				cout << "Job one has finished \n";
				cout << "And used page " << startpage1 << " to page " << endpage1 <<  endl;
			}
			ttr2--;
			if (ttr2 == 0)
			{

				cout << "Job two has finished \n";
				cout << "And used page " << startpage2 << " to page " << endpage2 << endl;
			}
			ttr3--;
			if (ttr3 == 0)
			{
				cout << "Job three has finished \n";
				cout << "And used page " << startpage3 << " to page " << endpage3 << endl;
			}
		}
	}
		if (pri1BIG)
		{
			for (int i = (ttr0 + ttr1 + ttr2 + ttr3 + 5); i > 0; i--)
			{
				ttr1--;
				if (ttr1 == 0)
				{
					cout << "Job one has finished \n";
					cout << "And used page " << startpage1 << " to page " << endpage1 << endl;

				}
				ttr0--;
				if (ttr0 == 0)
				{
					cout << "Job zero has finished \n";
					cout << "And used page " << startpage0 << " to page " << endpage0 << endl;
				}
				ttr2--;
				if (ttr2 == 0)
				{

					cout << "Job two has finished \n";
					cout << "And used page " << startpage2 << " to page " << endpage2 << endl;
				}
				ttr3--;
				if (ttr3 == 0)
				{
					cout << "Job three has finished \n";
					cout << "And used page " << startpage3 << " to page " << endpage3 << endl;
				}
			}
		}
			if (pri2BIG)
			{
				for (int i = (ttr0 + ttr1 + ttr2 + ttr3 + 5); i > 0; i--)
				{
					ttr2--;
					if (ttr2 == 0)
					{
						cout << "Job two has finished \n";
						cout << "And used page " << startpage2 << " to page " << endpage2 << endl;
					}
					ttr0--;
					if (ttr0 == 0)
					{
						cout << "Job zero has finished \n";
						cout << "And used page " << startpage0 << " to page " << endpage0 << endl;
					}
					ttr1--;
					if (ttr1 == 0)
					{

						cout << "Job one has finished \n";
						cout << "And used page " << startpage1 << " to page " << endpage1 << endl;
					}
					ttr3--;
					if (ttr3 == 0)
					{
						cout << "Job three has finished \n";
						cout << "And used page " << startpage3 << " to page " << endpage3 << endl;
					}
				}
			}
			if (pri3BIG)
			{
				for (int i = (ttr0 + ttr1 + ttr2 + ttr3 + 5); i > 0; i--)
				{
					ttr3--;
					if (ttr3 == 0)
					{
						cout << "Job three has finished \n";
						cout << "And used page " << startpage3 << " to page " << endpage3 << endl;
					}
					ttr0--;
					if (ttr0 == 0)
					{
						cout << "Job zero has finished \n";
						cout << "And used page " << startpage0 << " to page " << endpage0 << endl;
					}
					ttr1--;
					if (ttr1 == 0)
					{

						cout << "Job one has finished \n";
						cout << "And used page " << startpage1 << " to page " << endpage1 << endl;
					}
					ttr2--;
					if (ttr2 == 0)
					{
						cout << "Job two has finished \n";
						cout << "And used page " << startpage2 << " to page " << endpage2 << endl;
					}
				}
			}
	
	system("pause");
	return 0;
	
}
