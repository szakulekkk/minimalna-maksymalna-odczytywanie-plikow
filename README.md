#include <iostream>
#include <fstream>
#include <string>
using namespace std;

int main()
{
	fstream plik("dane.txt");
	string dane;

	while (getline(plik, dane))
	{
		cout << dane;
	}

	plik.close();

	string wartosc = "     ";
	int index = 0;
	float liczba;
	float min = 0;
	float max = 0;
	float srednia = 0;
	int pierwsza_spacja = 0;

	for (int i = 0; i < dane.length(); i++)
	{
		if (dane[i] != ' ')
		{
			wartosc[index] = dane[i];
			index++;
		}
		else
		{
			liczba = stof(wartosc);
			cout << liczba << "\n";

			if (pierwsza_spacja == 0)
			{
				min = liczba;
				pierwsza_spacja = 1;
			}
			else if (liczba < min)
			{
				min = liczba;
			}
			else if (liczba > max)
			{
				max = liczba;
			}
			wartosc = "    ";
			index = 0;
		}
	}

	cout << "\n\n * Minimalna temperatura wynosi " << min << " *";
	cout << "\n\n * Maksymalna temperatura wynosi " << max << " * \n\n";
	cout << srednia;
}
