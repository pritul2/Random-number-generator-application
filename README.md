#include <iostream>
#include <cstdio>

using namespace std;
int main()
{
	system("clear");
	int size = 0;
	int min = 0;
	int max = 0;
	cout << "enter the size of the array" << endl;
	cin >> size;
	system("clear");
	cout << "enter min value of range" << endl;
	cin >> min;
	cout << "enter max value of range" << endl;
	cout<<"enter the larger max value to avoid rpeatation"<<endl;
	cin >> max;
	system("clear");
	cout << "enter the 1 to include repeatation of numbers\nenter 2 to not include the repeatation" << endl;
	int repeat = 0;
	cin >> repeat;
	long int temp = 0;
	/*Exception handling for lack of number*/
	if(repeat==2 && max<size && min>max)
	{
		cout<<"lack of numbers to fit in array"<<endl;
		cout<<"try with different number"<<endl;
		return 0;
	}
	system("clear");
	if (repeat == 1)
	{
		for (int i = 0; i < size; i++)
		{
			temp = rand();
			if(temp<min) temp=min-temp;
			cout << temp % max << " ";
		}
		cout << endl;
	}
	else
	{
		for (int i = 0; i < size; i++)
		{
			temp=rand()%max;
			temp=(temp+i)%max;
			if(temp<min)
			{
				i--;
				continue;
			}
			cout<<temp<<" ";
		}
		cout << endl;
	}
}
