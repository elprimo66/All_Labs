#include <iostream>
#include <ctime>
#include <Windows.h>

using namespace std;


int main() {
	setlocale(0, "");

	int select;
	int countOfAnsver = 0;
	int attemps = 5;
	int ansverFromUser;
	char continuePlay = '1';
	char endOfPlay = '2';
	int randNumbers[3];

	cout << "\x1b[93m[1]Начать игру\x1b[0m" << endl;
	cout << "\x1b[93m[2]Выйти\x1b[0m" << endl;
	cout << "\x1b[93m[+]Выбирите пункт меню: \x1b[0m";

	cin >> select;
	cout << endl;

	if (select == 1) {

		srand(time(0));

		for (int i = 0; i < 3; i++)
		{
			randNumbers[i] = 1 + rand() % ((5 + 1) - 1);
		}

		while (attemps)
		{
			system("cls");
			cout << "\x1b[93m[+] Угаданных чисел [" << countOfAnsver << "/3]\x1b[0m" << endl;
			cout << "\x1b[93m[+] Попыток [" << attemps << "] \x1b[0m" << endl;
			cout << endl;



			cout << "\x1b[93m[>] Угадать число: \x1b[0m";
			cin >> ansverFromUser;
			cout << endl;

			//При правильном ответе
			if (ansverFromUser == randNumbers[0] || ansverFromUser == randNumbers[1] || ansverFromUser == randNumbers[2]) {

				countOfAnsver++;

				cout << "\x1b[92m[+] Вы угадали число!\x1b[0m" << endl;
				cout << endl;
				cout << "\x1b[96m[+] Правильные ответы" << endl;

				for (int i = 0; i < 3; i++)
				{
					cout << randNumbers[i] << endl;
				}
				cout << "\x1b[0m";

				Sleep(3500);

				for (int i = 0; i < 3; i++)
				{
					randNumbers[i] = 1 + rand() % ((5 + 1) - 1);
				}

				//Завершение игры (Выйгрыш)
				if (countOfAnsver == 3) {

					cout << endl;
					cout << "\x1b[92m[!] ВЫ ВЫЙГРАЛИ!!!\x1b[0m" << endl;
					cout << "\x1b[92m[!] Вы угадали все числа!\x1b[0m" << endl;

					cout << "\x1b[93m[+] Нажмите e, чтобы закончить\x1b[0m" << endl;
					cin >> endOfPlay;

					while (endOfPlay != 'e') {

						cout << "\x1b[93mНажмите e, чтобы закончить\x1b[0m" << endl;
						cin >> endOfPlay;
					}
					return 0;
				}
			}
			//Обработка введения исключительного значения (меньше 0 и больше 5)
			else if (ansverFromUser <= 0 || ansverFromUser > 5) {
				cout << "\x1b[93m[+] Ответ должен быть в диапащоне от 1 до 5" << endl;
				cout << "[+] Нажмите w, чтобы продолжить\x1b[0m" << endl;
				cin >> continuePlay;

				while (continuePlay != 'w') {
					cout << "\x1b[93mНажмите w, чтобы продолжить\x1b[0m" << endl;
					cin >> continuePlay;
				}

				system("CLS");
				continue;
			}
			//При неправильном ответе
			else
			{
				attemps--;
				cout << "\x1b[91m[-] Вы не угадали число!\x1b[0m" << endl;
				cout << "\x1b[96m[+] Правильные ответы" << endl;

				for (int i = 0; i < 3; i++)
				{
					cout << randNumbers[i] << endl;
				}
				cout << "\x1b[0m";

				Sleep(3500);
			}

		}

		//Завершение игры (Проигрыш)
		if (attemps == 0) {
			system("CLS");
			cout << "\x1b[91m[!] Вы проиграли!\x1b[0m" << endl;

			cout << "\x1b[93m[+] Нажмите e, чтобы закончить\x1b[0m" << endl;
			cin >> endOfPlay;

			while (endOfPlay != 'e') {

				cout << "\x1b[93mНажмите e, чтобы закончить\x1b[0m" << endl;
				cin >> endOfPlay;
			}
			return 0;
		}
	}
	else {
		return 0;
	}

	int _; cin >> _;
	return 0;
}



