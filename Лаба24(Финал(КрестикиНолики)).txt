#include <iostream>
#include <ctime>
#include <Windows.h>
using namespace std;

char SettingsOfTheme(char theme) {
	system("cls");
	cout << "\x1b[90m[0]Серый\x1b[0m" << endl;
	cout << "\x1b[91m[1]Красный" << endl;
	cout << "\x1b[92m[2]Зелёный" << endl;
	cout << "\x1b[93m[3]Желтый\x1b[0m" << endl;
	cout << "\x1b[94m[4]Голубой\x1b[0m" << endl;
	cout << "\x1b[95m[5]Пурпурный" << endl;
	cout << "\x1b[96m[6]Аква" << endl;
	cout << endl;

	cout << "\x1b[9" << theme << "m[+]Выберите цвет темы: \x1b[0m";

	cin >> theme;
	switch (theme)
	{
	case '1':
	case '2':
	case '3':
	case '4':
	case '5':
	case '6':
	case '0':
		return theme;
		break;
	default:
		cout << "\x1b[91m[+]Выбор должен быть: от 0 до 6 \x1b[0m" << endl;
		Sleep(1500);
		SettingsOfTheme(theme);
	}
}

char Menu(char select, char theme) {
	system("cls");
	cout << "\x1b[9" << theme << "m____М Е Н Ю____\n";
	cout << "\x1b[9" << theme << "m[1] Начать игру\n";
	cout << "\x1b[9" << theme << "m[2] Статистика\n";
	cout << "\x1b[9" << theme << "m[3] Настройки\n";
	cout << "\x1b[9" << theme << "m[4] Выйти\n";
	cout << "\x1b[9" << theme << "m[+] Выбирите пункт меню: ";

	cin >> select;
	switch (select)
	{
	case '1':
	case '2':
	case '3':
	case '4':
		return select;
		break;
	default:
		cout << "\x1b[91m[+]Ответ должен быть: от 1 до 4 \x1b[0m" << endl;
		Sleep(1500);
		Menu(select, theme);
	}
}

string SettingsOfNik(char theme) {
	string name = "";
	system("cls");
	cout << "\x1b[9" << theme << "m[+] Напишите новое имя игрока:\x1b[0m";
	cin >> name;
	return name;
}

char SettingsOfFigure(char theme) {
	char figure = '-';
	system("cls");
	cout << "\x1b[9" << theme << "m[+] Введите символ:\x1b[0m";
	cin >> figure;
	return figure;
}

char SettingsOfColor(char theme) {
	char color = '-';
	system("cls");
	cout << "\x1b[90m[0]Серый\x1b[0m" << endl;
	cout << "\x1b[91m[1]Красный" << endl;
	cout << "\x1b[92m[2]Зелёный" << endl;
	cout << "\x1b[93m[3]Желтый\x1b[0m" << endl;
	cout << "\x1b[94m[4]Голубой\x1b[0m" << endl;
	cout << "\x1b[95m[5]Пурпурный" << endl;
	cout << "\x1b[96m[6]Аква" << endl;
	cout << endl;

	cout << "\x1b[9" << theme << "m[+]Введите цвет: \x1b[0m";

	cin >> color;
	switch (color)
	{
	case '1':
	case '2':
	case '3':
	case '4':
	case '5':
	case '6':
	case '0':
		return color;
		break;
	default:
		cout << "\x1b[91m[+]Ответ должен быть: от 0 до 6 \x1b[0m" << endl;
		Sleep(1500);
		SettingsOfColor(theme);
	}
}


int MenuSettingsOfPlayer(char select, string name1, string name2, char figure1, char figure2, char color1, char color2, char theme) {
	string name;
	char figure;
	char color;
	system("cls");

	if (select == '1') {
		name = name1;
		figure = figure1;
		color = color1;
	}
	else {
		name = name2;
		figure = figure2;
		color = color2;
	}
	cout << "\x1b[9" << theme << "mНастройка Игрока" << "[" << select << "]\n";
	cout << "\x1b[9" << theme << "m[1] Ник    : " << name << "\n";
	cout << "\x1b[9" << theme << "m[2] Фигура : " << figure << "\n";
	cout << "\x1b[9" << theme << "m[3] Цвет   : ";
	switch (color)
	{
	case '1':
		cout << "\x1b[9" << color << "mКрасный" << "\n\x1b[0m";
		break;
	case '2':
		cout << "\x1b[9" << color << "mЗелёный" << "\n\x1b[0m";
		break;
	case '3':
		cout << "\x1b[9" << color << "mЖёлтый" << "\n\x1b[0m";
		break;
	case '4':
		cout << "\x1b[9" << color << "mГолубой" << "\n\x1b[0m";
		break;
	case '5':
		cout << "\x1b[9" << color << "mПурпурный" << "\n\x1b[0m";
		break;
	case '6':
		cout << "\x1b[9" << color << "mАква" << "\n\x1b[0m";
		break;
	case '0':
		cout << "\x1b[9" << color << "mСерый" << "\n\x1b[0m";
		break;
	default:
		cout << "\x1b[91m[!] Нет такого цвета\n\x1b[0m";
		break;
	}
	cout << "\x1b[9" << theme << "m[4] Назад" << "\n";

	cout << "\x1b[9" << theme << "m[+] Выбирите пункт меню: \n";
	cin >> select;
	switch (select)
	{
	case '1':
	case '2':
	case '3':
	case '4':
		return select;
	default:
		cout << "\x1b[91m[+]Ответ должен быть: от 1 до 4 \x1b[0m" << endl;
		Sleep(1500);
		MenuSettingsOfPlayer(select, name1, name2, figure1, figure2, color1, color2, theme);
		break;
	}
}

void Statistics(char select, int resPlay, int winP1, int winP2, int winC, int draw, char theme, string name1, string name2) {
	system("cls");
	cout << "\x1b[9" << theme << "m--- Статистика ---\n";
	cout << "\x1b[9" << theme << "m[+] Колличество выйгранных игр игроком " << name1 << ": " << winP1 << "\n";
	cout << "\x1b[9" << theme << "m[+] Колличество выйгранных игр игроком " << name2 << ": " << winP2 << "\n";
	cout << "\x1b[9" << theme << "m[+] Колличество выйгранных игр компьютером: " << winC << "\n";
	cout << "\x1b[9" << theme << "m[+] Колличество игр с результатом ' ничья '" ": " << draw << "\n";
	cout << "\x1b[9" << theme << "m[1] Назад\n";
	cin >> select;
	if (select != '1') {
		cout << "\x1b[91m[+] Используйте указанные для навигации символы и цыфры!!\n\x1b[0m";
		Sleep(3000);
		Statistics(select, resPlay, winP1, winP2, winC, draw, theme, name1, name2);
	}
}

char Setings(char theme) {
	system("cls");
	char select;

	cout << "\x1b[9" << theme << "m[+] Настройки\n";
	cout << "\x1b[9" << theme << "m[1] Игрок 1\n";
	cout << "\x1b[9" << theme << "m[2] Игрок 2\n";
	cout << "\x1b[9" << theme << "m[3] Тема\n";
	cout << "\x1b[9" << theme << "m[4] Выход в меню\n";
	cout << "\x1b[9" << theme << "m[+] Выберите: ";
	cin >> select;

	switch (select)
	{
	case '1':
	case '2':
	case '3':
	case '4':
		return select;
		break;
	default:
		cout << "\x1b[91m[+] Используйте указанные для навигации символы и цыфры!!\n\x1b[0m";
		Sleep(3000);
		Setings(theme);
		break;
	}

}

int Exit(char select, char theme) {
	return 0;
}

char MenuPlay(char select, char theme) {
	system("cls");
	cout << "\x1b[9" << theme << "m____К Р Е С Т И К И - Н О Л И К И____\x1b[0m\n\n";
	cout << "\x1b[9" << theme << "m[+] Варианты игры\x1b[0m\n\n";
	cout << "\x1b[9" << theme << "m[1] Одиночная\x1b[0m\n";
	cout << "\x1b[9" << theme << "m[2] С другом\x1b[0m\n";
	cout << "\x1b[9" << theme << "m[3] Назад\x1b[0m\n\n";

	cout << "\x1b[9" << theme << "m[+] Выберите свою игру: \x1b[0m";

	cin >> select;
	switch (select)
	{
	case '1':
	case '2':
	case '3':
		return select;
		break;
	default:
		cout << "\x1b[91m[+]Ответ должен быть: 1, 2 или 3 \x1b[0m" << endl;
		Sleep(1500);
		MenuPlay(select, theme);
	}
}

int PlaySolo(char select, string name1, char figure1, char color1, char figure2, char theme) {
	system("cls");
	srand(time(0));
	int selectC;
	int numberOfSteps = 0;
	bool mark = 0;
	int win = 0;
	int queue = 0;
	int step = 0;
	int space[3][3]{ { 0,0,0 }, {0, 0, 0}, {0, 0, 0} };
	string playSpaceTxt[7][16]{
		{" " , "1" , " " , "|" , " " , "2" , " " , "|" , " " , "3" , " " ,	"		",	"Информация: ", "", "", ""},
		{"-" , "-" , "-" , "-" , "-" , "-" , "-" , "-" , "-" , "-" , "-" ,	"		",	"",				"", "", ""},
		{" " , "4" , " " , "|" , " " , "5" , " " , "|" , " " , "6" , " " ,	"		",	"",				"",	"", ""},
		{"-" , "-" , "-" , "-" , "-" , "-" , "-" , "-" , "-" , "-" , "-" ,	"		",	"",				"",	"", ""},
		{" " , "7" , " " , "|" , " " , "8" , " " , "|" , " " , "9" , " " ,	"		",	"",				"",	"", ""},
		{" " , " " , " " , " " , " " , " " , " " , " " , " " , " " , " " ,	"		",	"",				"",	"", ""},
		{" " , "Х" , "о" , "д" , "и" , "т" , ":" , " " , " " , " " , " " ,  "		",	"",				"",	"", ""}
	};

	bool left1, midlV1, right1;
	bool top1, midl1, button1;
	//начинается с верхнего левого угла
	bool LDiagonal1;
	//начинается с верхнего правого угла
	bool RDiagonal1;

	//-----------------------------------

	bool left2, midlV2, right2;
	bool top2, midl2, button2;
	//начинается с верхнего левого угла
	bool LDiagonal2;
	//начинается с верхнего правого угла
	bool RDiagonal2;

	while (win == 0)
	{
		system("cls");

		cout << "\x1b[9" << theme << "m**** К Р Е С Т И К И - Н О Л И К И ****\x1b[0m\n\n";

		queue++;
		step++;
		numberOfSteps++;


		if (queue % 2 == 1)
		{
			playSpaceTxt[6][8] = name1;
		}
		else
		{
			playSpaceTxt[6][8] = "Компьютер";
		}

		for (int y = 0; y < 7; y++)
		{
			for (int x = 0; x < 16; x++)
			{
				cout << "\x1b[9" << theme << "m" << playSpaceTxt[y][x];
			}
			cout << endl;
		}

		if (queue % 2 == 1)
		{
			cout << "\x1b[9" << theme << "m[+] Введите ячейку: \x1b[0m";
			cin >> select;

			while (select != '1' && select != '2' && select != '3' && select != '4' && select != '5' && select != '6' && select != '7' && select != '8' && select != '9') {
				cout << "\x1b[9" << theme << "m[+] Неправильное значение\nВыбирите другое значение: \x1b[0m";
				cin >> select;
			}

			while (mark == 0)
			{
				switch (select)
				{
				case '1':
					if (playSpaceTxt[0][1] != "1")
					{
						while (select == '1') {
							cout << "\x1b[9" << theme << "m[+] Ячейка занята!\nВыбирите другую ячейку: \x1b[0m";
							cin >> select;
						}
						break;
					}
					playSpaceTxt[0][1] = figure1;
					playSpaceTxt[step][13] = "Игрок: " + name1;
					playSpaceTxt[step][15] = " Сходил на ячейку: 1";
					space[0][0] = 1;
					mark = 1;
					break;
				case '2':
					if (playSpaceTxt[0][5] != "2")
					{
						while (select == '2') {
							cout << "\x1b[9" << theme << "m[+] Ячейка занята!\nВыбирите другую ячейку: \x1b[0m";
							cin >> select;
						}
						break;
					}
					playSpaceTxt[0][5] = figure1;
					playSpaceTxt[step][13] = "Игрок: " + name1;
					playSpaceTxt[step][15] = " Сходил на ячейку: 2";
					space[0][1] = 1;
					mark = 1;
					break;
				case '3':
					if (playSpaceTxt[0][9] != "3")
					{
						while (select == '3') {
							cout << "\x1b[9" << theme << "m[+] Ячейка занята!\nВыбирите другую ячейку: \x1b[0m";
							cin >> select;
						}
						break;
					}
					playSpaceTxt[0][9] = figure1;
					playSpaceTxt[step][13] = "Игрок: " + name1;
					playSpaceTxt[step][15] = " Сходил на ячейку: 3";
					space[0][2] = 1;
					mark = 1;
					break;
				case '4':
					if (playSpaceTxt[2][1] != "4")
					{
						while (select == '4') {
							cout << "\x1b[9" << theme << "m[+] Ячейка занята!\nВыбирите другую ячейку: \x1b[0m";
							cin >> select;
						}
						break;
					}
					playSpaceTxt[2][1] = figure1;
					playSpaceTxt[step][13] = "Игрок: " + name1;
					playSpaceTxt[step][15] = " Сходил на ячейку: 4";
					space[1][0] = 1;
					mark = 1;
					break;
				case '5':
					if (playSpaceTxt[2][5] != "5")
					{
						while (select == '5') {
							cout << "\x1b[9" << theme << "m[+] Ячейка занята!\nВыбирите другую ячейку: \x1b[0m";
							cin >> select;
						}
						break;
					}
					playSpaceTxt[2][5] = figure1;
					playSpaceTxt[step][13] = "Игрок: " + name1;
					playSpaceTxt[step][15] = " Сходил на ячейку: 5";
					space[1][1] = 1;
					mark = 1;
					break;
				case '6':
					if (playSpaceTxt[2][9] != "6")
					{
						while (select == '6') {
							cout << "\x1b[9" << theme << "m[+] Ячейка занята!\nВыбирите другую ячейку: \x1b[0m";
							cin >> select;
						}
						break;
					}
					playSpaceTxt[2][9] = figure1;
					playSpaceTxt[step][13] = "Игрок: " + name1;
					playSpaceTxt[step][15] = " Сходил на ячейку: 6";
					space[1][2] = 1;
					mark = 1;
					break;
				case '7':
					if (playSpaceTxt[4][1] != "7")
					{
						while (select == '7') {
							cout << "\x1b[9" << theme << "m[+] Ячейка занята!\nВыбирите другую ячейку: \x1b[0m";
							cin >> select;
						}
						break;
					}
					playSpaceTxt[4][1] = figure1;
					playSpaceTxt[step][13] = "Игрок: " + name1;
					playSpaceTxt[step][15] = " Сходил на ячейку: 7";
					space[2][0] = 1;
					mark = 1;
					break;
				case '8':
					if (playSpaceTxt[4][5] != "8")
					{
						while (select == '8') {
							cout << "\x1b[9" << theme << "m[+] Ячейка занята!\nВыбирите другую ячейку: \x1b[0m";
							cin >> select;
						}
						break;
					}
					playSpaceTxt[4][5] = figure1;
					playSpaceTxt[step][13] = "Игрок: " + name1;
					playSpaceTxt[step][15] = " Сходил на ячейку: 8";
					space[2][1] = 1;
					mark = 1;
					break;
				case '9':
					if (playSpaceTxt[4][9] != "9")
					{
						while (select == '9') {
							cout << "\x1b[9" << theme << "m[+] Ячейка занята!\nВыбирите другую ячейку: \x1b[0m";
							cin >> select;
						}
						break;
					}
					playSpaceTxt[4][9] = figure1;
					playSpaceTxt[step][13] = "Игрок: " + name1;
					playSpaceTxt[step][15] = " Сходил на ячейку: 9";
					space[2][2] = 1;
					mark = 1;
					break;
				default:
					break;
				}
			}
			mark = 0;
		}
		else
		{
			selectC = 1 + rand() % ((9 + 1) - 1);
			while (mark == 0)
			{
				switch (selectC)
				{
				case 1:
					if (playSpaceTxt[0][1] != "1")
					{
						while (selectC == 1) {
							selectC = 1 + rand() % ((9 + 1) - 1);
						}
						break;
					}
					playSpaceTxt[0][1] = figure2;
					playSpaceTxt[step][13] = "Игрок: Компьютер";
					playSpaceTxt[step][15] = " Сходил на ячейку: 1";
					space[0][0] = 2;
					mark = 1;
					break;
				case 2:
					if (playSpaceTxt[0][5] != "2")
					{
						while (selectC == 2) {
							selectC = 1 + rand() % ((9 + 1) - 1);
						}
						break;
					}
					playSpaceTxt[0][5] = figure2;
					playSpaceTxt[step][13] = "Игрок: Компьютер";
					playSpaceTxt[step][15] = " Сходил на ячейку: 2";
					space[0][1] = 2;
					mark = 1;
					break;
				case 3:
					if (playSpaceTxt[0][9] != "3")
					{
						while (selectC == 3) {
							selectC = 1 + rand() % ((9 + 1) - 1);
						}
						break;
					}
					playSpaceTxt[0][9] = figure2;
					playSpaceTxt[step][13] = "Игрок: Компьютер";
					playSpaceTxt[step][15] = "Сходил на ячейку: 3";
					space[0][2] = 2;
					mark = 1;
					break;
				case 4:
					if (playSpaceTxt[2][1] != "4")
					{
						while (selectC == 4) {
							selectC = 1 + rand() % ((9 + 1) - 1);
						}
						break;
					}
					playSpaceTxt[2][1] = figure2;
					playSpaceTxt[step][13] = "Игрок: Компьютер";
					playSpaceTxt[step][15] = " Сходил на ячейку: 4";
					space[1][0] = 2;
					mark = 1;
					break;
				case 5:
					if (playSpaceTxt[2][5] != "5")
					{
						while (selectC == 5) {
							selectC = 1 + rand() % ((9 + 1) - 1);
						}
						break;
					}
					playSpaceTxt[2][5] = figure2;
					playSpaceTxt[step][13] = "Игрок: Компьютер";
					playSpaceTxt[step][15] = " Сходил на ячейку: 5";
					space[1][1] = 2;
					mark = 1;
					break;
				case 6:
					if (playSpaceTxt[2][9] != "6")
					{
						while (selectC == 6) {
							selectC = 1 + rand() % ((9 + 1) - 1);
						}
						break;
					}
					playSpaceTxt[2][9] = figure2;
					playSpaceTxt[step][13] = "Игрок: Компьютер";
					playSpaceTxt[step][15] = " Сходил на ячейку: 6";
					space[1][2] = 2;
					mark = 1;
					break;
				case 7:
					if (playSpaceTxt[4][1] != "7")
					{
						while (selectC == 7) {
							selectC = 1 + rand() % ((9 + 1) - 1);
						}
						break;
					}
					playSpaceTxt[4][1] = figure2;
					playSpaceTxt[step][13] = "Игрок: Компьютер";
					playSpaceTxt[step][15] = " Сходил на ячейку: 7";
					space[2][0] = 2;
					mark = 1;
					break;
				case 8:
					if (playSpaceTxt[4][5] != "8")
					{
						while (selectC == 8) {
							selectC = 1 + rand() % ((9 + 1) - 1);
						}
						break;
					}
					playSpaceTxt[4][5] = figure2;
					playSpaceTxt[step][13] = "Игрок: Компьютер";
					playSpaceTxt[step][15] = " Сходил на ячейку: 8";
					space[2][1] = 2;
					mark = 1;
					break;
				case 9:
					if (playSpaceTxt[4][9] != "9")
					{
						while (selectC == 9) {
							selectC = 1 + rand() % ((9 + 1) - 1);
						}
						break;
					}
					playSpaceTxt[4][9] = figure2;
					playSpaceTxt[step][13] = "Игрок: Компьютер";
					playSpaceTxt[step][15] = " Сходил на ячейку: 9";
					space[2][2] = 2;
					mark = 1;
					break;
				default:
					break;
				}
			}
			mark = 0;
		}
		if (step == 5)
		{
			step = 0;
		}
		left1 = (space[0][0] & space[1][0] & space[2][0]) == 1;
		midlV1 = (space[0][1] & space[1][1] & space[2][1]) == 1;
		right1 = (space[0][2] & space[1][2] & space[2][2]) == 1;

		top1 = (space[0][0] & space[0][1] & space[0][2]) == 1;
		midl1 = (space[1][0] & space[1][1] & space[1][2]) == 1;
		button1 = (space[2][0] & space[2][1] & space[2][2]) == 1;

		//начинается с верхнего левого угла
		LDiagonal1 = (space[0][0] & space[1][1] & space[2][2]) == 1;
		//начинается с верхнего правого угла
		RDiagonal1 = (space[0][2] & space[1][1] & space[2][0]) == 1;

		//::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::

		left2 = (space[0][0] & space[1][0] & space[2][0]) == 2;
		midlV2 = (space[0][1] & space[1][1] & space[2][1]) == 2;
		right2 = (space[0][2] & space[1][2] & space[2][2]) == 2;

		top2 = (space[0][0] & space[0][1] & space[0][2]) == 2;
		midl2 = (space[1][0] & space[1][1] & space[1][2]) == 2;
		button2 = (space[2][0] & space[2][1] & space[2][2]) == 2;

		//начинается с верхнего левого угла
		LDiagonal2 = (space[0][0] & space[1][1] & space[2][2]) == 2;
		//начинается с верхнего правого угла
		RDiagonal2 = (space[0][2] & space[1][1] & space[2][0]) == 2;

		if (left1 || midl1 || right1 || top1 || midlV1 || button1 || LDiagonal1 || RDiagonal1) {
			system("cls");
			cout << "\x1b[9" << theme << "m * * * * К О Н Е Ц  И Г Р Ы * * * * \x1bm\n";
			cout << "\x1b[9" << theme << "m         ВЫЙГРАЛ ИГРОК: " << name1 << "\x1bm\n\n";
			win = 1;
			cout << "\x1b[9" << theme << "mНажмите клавишу, чтобы продолжить: \x1bm";
			cin >> select;
			return 1;
		}
		else if (left2 || midl2 || right2 || top2 || midlV2 || button2 || LDiagonal2 || RDiagonal2) {
			system("cls");
			cout << "\x1b[9" << theme << "m * * * * К О Н Е Ц  И Г Р Ы * * * * \x1bm\n\n";
			cout << "\x1b[9" << theme << "m         ВЫЙГРАЛ ИГРОК: " << "Компьютер" << "\x1bm\n";
			win = 2;
			cout << "\x1b[9" << theme << "mНажмите клавишу, чтобы продолжить: \x1bm";
			cin >> select;
			return 2;
		}
		else if (numberOfSteps == 9)
		{
			system("cls");
			cout << "\x1b[9" << theme << "m * * * * К О Н Е Ц  И Г Р Ы * * * * \x1bm\n";
			cout << "\x1b[9" << theme << "m           ! Н И Ч Ь Я !\x1bm\n";
			cout << "\x1b[9" << theme << "m!!! П О Б И Д И Л А  Д Р У Ж Б А !!!\x1bm\n\n";

			win = 3;
			cout << "\x1b[9" << theme << "mНажмите клавишу, чтобы продолжить: \x1bm";
			cin >> select;
			return 3;
		}
	}
}

int PlayDuo(char select, string name1, char figure1, char color1, string name2, char figure2, char color2, char theme) {
	system("cls");
	int numberOfSteps = 0;
	bool mark = 0;
	int win = 0;
	int queue = 0;
	int step = 0;
	int space[3][3]{ { 0,0,0 }, {0, 0, 0}, {0, 0, 0} };
	string playSpaceTxt[7][16]{
		{" " , "1" , " " , "|" , " " , "2" , " " , "|" , " " , "3" , " " ,	"		",	"Информация: ", "", "", ""},
		{"-" , "-" , "-" , "-" , "-" , "-" , "-" , "-" , "-" , "-" , "-" ,	"		",	"",				"", "", ""},
		{" " , "4" , " " , "|" , " " , "5" , " " , "|" , " " , "6" , " " ,	"		",	"",				"",	"", ""},
		{"-" , "-" , "-" , "-" , "-" , "-" , "-" , "-" , "-" , "-" , "-" ,	"		",	"",				"",	"", ""},
		{" " , "7" , " " , "|" , " " , "8" , " " , "|" , " " , "9" , " " ,	"		",	"",				"",	"", ""},
		{" " , " " , " " , " " , " " , " " , " " , " " , " " , " " , " " ,	"		",	"",				"",	"", ""},
		{" " , "Х" , "о" , "д" , "и" , "т" , ":" , " " , " " , " " , " " ,  "		",	"",				"",	"", ""}
	};

	bool left1, midlV1, right1;
	bool top1, midl1, button1;
	//начинается с верхнего левого угла
	bool LDiagonal1;
	//начинается с верхнего правого угла
	bool RDiagonal1;

	//-----------------------------------

	bool left2, midlV2, right2;
	bool top2, midl2, button2;
	//начинается с верхнего левого угла
	bool LDiagonal2;
	//начинается с верхнего правого угла
	bool RDiagonal2;

	while (win == 0)
	{
		system("cls");

		cout << "\x1b[9" << theme << "m**** К Р Е С Т И К И - Н О Л И К И ****\x1b[0m\n\n";

		queue++;
		step++;
		numberOfSteps++;


		if (queue % 2 == 1)
		{
			playSpaceTxt[6][8] = name1;
		}
		else
		{
			playSpaceTxt[6][8] = name2;
		}

		for (int y = 0; y < 7; y++)
		{
			for (int x = 0; x < 16; x++)
			{
				cout << "\x1b[9" << theme << "m" << playSpaceTxt[y][x];
			}
			cout << endl;
		}
		cout << "\x1b[9" << theme << "m[+] Введите ячейку: \x1b[0m";
		cin >> select;

		while (select != '1' && select != '2' && select != '3' && select != '4' && select != '5' && select != '6' && select != '7' && select != '8' && select != '9') {
			cout << "\x1b[9" << theme << "m[+] Неправильное значение\nВыбирите другое значение: \x1b[0m";
			cin >> select;
		}

		if (queue % 2 == 1)
		{
			while (mark == 0)
			{
				switch (select)
				{
				case '1':
					if (playSpaceTxt[0][1] != "1")
					{
						while (select == '1') {
							cout << "\x1b[9" << theme << "m[+] Ячейка занята!\nВыбирите другую ячейку: \x1b[0m";
							cin >> select;
						}
						break;
					}
					playSpaceTxt[0][1] = figure1;
					playSpaceTxt[step][13] = "Игрок: " + name1;
					playSpaceTxt[step][15] = " Сходил на ячейку: 1";
					space[0][0] = 1;
					mark = 1;
					break;
				case '2':
					if (playSpaceTxt[0][5] != "2")
					{
						while (select == '2') {
							cout << "\x1b[9" << theme << "m[+] Ячейка занята!\nВыбирите другую ячейку: \x1b[0m";
							cin >> select;
						}
						break;
					}
					playSpaceTxt[0][5] = figure1;
					playSpaceTxt[step][13] = "Игрок: " + name1;
					playSpaceTxt[step][15] = " Сходил на ячейку: 2";
					space[0][1] = 1;
					mark = 1;
					break;
				case '3':
					if (playSpaceTxt[0][9] != "3")
					{
						while (select == '3') {
							cout << "\x1b[9" << theme << "m[+] Ячейка занята!\nВыбирите другую ячейку: \x1b[0m";
							cin >> select;
						}
						break;
					}
					playSpaceTxt[0][9] = figure1;
					playSpaceTxt[step][13] = "Игрок: " + name1;
					playSpaceTxt[step][15] = " Сходил на ячейку: 3";
					space[0][2] = 1;
					mark = 1;
					break;
				case '4':
					if (playSpaceTxt[2][1] != "4")
					{
						while (select == '4') {
							cout << "\x1b[9" << theme << "m[+] Ячейка занята!\nВыбирите другую ячейку: \x1b[0m";
							cin >> select;
						}
						break;
					}
					playSpaceTxt[2][1] = figure1;
					playSpaceTxt[step][13] = "Игрок: " + name1;
					playSpaceTxt[step][15] = " Сходил на ячейку: 4";
					space[1][0] = 1;
					mark = 1;
					break;
				case '5':
					if (playSpaceTxt[2][5] != "5")
					{
						while (select == '5') {
							cout << "\x1b[9" << theme << "m[+] Ячейка занята!\nВыбирите другую ячейку: \x1b[0m";
							cin >> select;
						}
						break;
					}
					playSpaceTxt[2][5] = figure1;
					playSpaceTxt[step][13] = "Игрок: " + name1;
					playSpaceTxt[step][15] = " Сходил на ячейку: 5";
					space[1][1] = 1;
					mark = 1;
					break;
				case '6':
					if (playSpaceTxt[2][9] != "6")
					{
						while (select == '6') {
							cout << "\x1b[9" << theme << "m[+] Ячейка занята!\nВыбирите другую ячейку: \x1b[0m";
							cin >> select;
						}
						break;
					}
					playSpaceTxt[2][9] = figure1;
					playSpaceTxt[step][13] = "Игрок: " + name1;
					playSpaceTxt[step][15] = " Сходил на ячейку: 6";
					space[1][2] = 1;
					mark = 1;
					break;
				case '7':
					if (playSpaceTxt[4][1] != "7")
					{
						while (select == '7') {
							cout << "\x1b[9" << theme << "m[+] Ячейка занята!\nВыбирите другую ячейку: \x1b[0m";
							cin >> select;
						}
						break;
					}
					playSpaceTxt[4][1] = figure1;
					playSpaceTxt[step][13] = "Игрок: " + name1;
					playSpaceTxt[step][15] = " Сходил на ячейку: 7";
					space[2][0] = 1;
					mark = 1;
					break;
				case '8':
					if (playSpaceTxt[4][5] != "8")
					{
						while (select == '8') {
							cout << "\x1b[9" << theme << "m[+] Ячейка занята!\nВыбирите другую ячейку: \x1b[0m";
							cin >> select;
						}
						break;
					}
					playSpaceTxt[4][5] = figure1;
					playSpaceTxt[step][13] = "Игрок: " + name1;
					playSpaceTxt[step][15] = " Сходил на ячейку: 8";
					space[2][1] = 1;
					mark = 1;
					break;
				case '9':
					if (playSpaceTxt[4][9] != "9")
					{
						while (select == '9') {
							cout << "\x1b[9" << theme << "m[+] Ячейка занята!\nВыбирите другую ячейку: \x1b[0m";
							cin >> select;
						}
						break;
					}
					playSpaceTxt[4][9] = figure1;
					playSpaceTxt[step][13] = "Игрок: " + name1;
					playSpaceTxt[step][15] = " Сходил на ячейку: 9";
					space[2][2] = 1;
					mark = 1;
					break;
				default:
					break;
				}
			}
			mark = 0;
		}
		else
		{
			while (mark == 0)
			{
				switch (select)
				{
				case '1':
					if (playSpaceTxt[0][1] != "1")
					{
						while (select == '1') {
							cout << "\x1b[9" << theme << "m[+] Ячейка занята!\nВыбирите другую ячейку: \x1b[0m";
							cin >> select;
						}
						break;
					}
					playSpaceTxt[0][1] = figure2;
					playSpaceTxt[step][13] = "Игрок: " + name2;
					playSpaceTxt[step][15] = " Сходил на ячейку: 1";
					space[0][0] = 2;
					mark = 1;
					break;
				case '2':
					if (playSpaceTxt[0][5] != "2")
					{
						while (select == '2') {
							cout << "\x1b[9" << theme << "m[+] Ячейка занята!\nВыбирите другую ячейку: \x1b[0m";
							cin >> select;
						}
						break;
					}
					playSpaceTxt[0][5] = figure2;
					playSpaceTxt[step][13] = "Игрок: " + name2;
					playSpaceTxt[step][15] = " Сходил на ячейку: 2";
					space[0][1] = 2;
					mark = 1;
					break;
				case '3':
					if (playSpaceTxt[0][9] != "3")
					{
						while (select == '3') {
							cout << "\x1b[9" << theme << "m[+] Ячейка занята!\nВыбирите другую ячейку: \x1b[0m";
							cin >> select;
						}
						break;
					}
					playSpaceTxt[0][9] = figure2;
					playSpaceTxt[step][13] = "Игрок: " + name2;
					playSpaceTxt[step][15] = " Сходил на ячейку: 3";
					space[0][2] = 2;
					mark = 1;
					break;
				case '4':
					if (playSpaceTxt[2][1] != "4")
					{
						while (select == '4') {
							cout << "\x1b[9" << theme << "m[+] Ячейка занята!\nВыбирите другую ячейку: \x1b[0m";
							cin >> select;
						}
						break;
					}
					playSpaceTxt[2][1] = figure2;
					playSpaceTxt[step][13] = "Игрок: " + name2;
					playSpaceTxt[step][15] = " Сходил на ячейку: 4";
					space[1][0] = 2;
					mark = 1;
					break;
				case '5':
					if (playSpaceTxt[2][5] != "5")
					{
						while (select == '5') {
							cout << "\x1b[9" << theme << "m[+] Ячейка занята!\nВыбирите другую ячейку: \x1b[0m";
							cin >> select;
						}
						break;
					}
					playSpaceTxt[2][5] = figure2;
					playSpaceTxt[step][13] = "Игрок: " + name2;
					playSpaceTxt[step][15] = " Сходил на ячейку: 5";
					space[1][1] = 2;
					mark = 1;
					break;
				case '6':
					if (playSpaceTxt[2][9] != "6")
					{
						while (select == '6') {
							cout << "\x1b[9" << theme << "m[+] Ячейка занята!\nВыбирите другую ячейку: \x1b[0m";
							cin >> select;
						}
						break;
					}
					playSpaceTxt[2][9] = figure2;
					playSpaceTxt[step][13] = "Игрок: " + name2;
					playSpaceTxt[step][15] = " Сходил на ячейку: 6";
					space[1][2] = 2;
					mark = 1;
					break;
				case '7':
					if (playSpaceTxt[4][1] != "7")
					{
						while (select == '7') {
							cout << "\x1b[9" << theme << "m[+] Ячейка занята!\nВыбирите другую ячейку: \x1b[0m";
							cin >> select;
						}
						break;
					}
					playSpaceTxt[4][1] = figure2;
					playSpaceTxt[step][13] = "Игрок: " + name2;
					playSpaceTxt[step][15] = " Сходил на ячейку: 7";
					space[2][0] = 2;
					mark = 1;
					break;
				case '8':
					if (playSpaceTxt[4][5] != "8")
					{
						while (select == '8') {
							cout << "\x1b[9" << theme << "m[+] Ячейка занята!\nВыбирите другую ячейку: \x1b[0m";
							cin >> select;
						}
						break;
					}
					playSpaceTxt[4][5] = figure2;
					playSpaceTxt[step][13] = "Игрок: " + name2;
					playSpaceTxt[step][15] = " Сходил на ячейку: 8";
					space[2][1] = 2;
					mark = 1;
					break;
				case '9':
					if (playSpaceTxt[4][9] != "9")
					{
						while (select == '9') {
							cout << "\x1b[9" << theme << "m[+] Ячейка занята!\nВыбирите другую ячейку: \x1b[0m";
							cin >> select;
						}
						break;
					}
					playSpaceTxt[4][9] = figure2;
					playSpaceTxt[step][13] = "Игрок: " + name2;
					playSpaceTxt[step][15] = " Сходил на ячейку: 9";
					space[2][2] = 2;
					mark = 1;
					break;
				default:
					break;
				}
			}
			mark = 0;
		}
		if (step == 5)
		{
			step = 0;
		}
		left1 = (space[0][0] & space[1][0] & space[2][0]) == 1;
		midlV1 = (space[0][1] & space[1][1] & space[2][1]) == 1;
		right1 = (space[0][2] & space[1][2] & space[2][2]) == 1;

		top1 = (space[0][0] & space[0][1] & space[0][2]) == 1;
		midl1 = (space[1][0] & space[1][1] & space[1][2]) == 1;
		button1 = (space[2][0] & space[2][1] & space[2][2]) == 1;

		//начинается с верхнего левого угла
		LDiagonal1 = (space[0][0] & space[1][1] & space[2][2]) == 1;
		//начинается с верхнего правого угла
		RDiagonal1 = (space[0][2] & space[1][1] & space[2][0]) == 1;

		//::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::

		left2 = (space[0][0] & space[1][0] & space[2][0]) == 2;
		midlV2 = (space[0][1] & space[1][1] & space[2][1]) == 2;
		right2 = (space[0][2] & space[1][2] & space[2][2]) == 2;

		top2 = (space[0][0] & space[0][1] & space[0][2]) == 2;
		midl2 = (space[1][0] & space[1][1] & space[1][2]) == 2;
		button2 = (space[2][0] & space[2][1] & space[2][2]) == 2;

		//начинается с верхнего левого угла
		LDiagonal2 = (space[0][0] & space[1][1] & space[2][2]) == 2;
		//начинается с верхнего правого угла
		RDiagonal2 = (space[0][2] & space[1][1] & space[2][0]) == 2;

		if (left1 || midl1 || right1 || top1 || midlV1 || button1 || LDiagonal1 || RDiagonal1) {
			system("cls");
			cout << "\x1b[9" << theme << "m * * * * К О Н Е Ц  И Г Р Ы * * * * \x1bm\n";
			cout << "\x1b[9" << theme << "m         ВЫЙГРАЛ ИГРОК: " << name1 << "\x1bm\n\n";
			win = 1;
			cout << "\x1b[9" << theme << "mНажмите клавишу, чтобы продолжить: \x1bm";
			cin >> select;
			return 1;
		}
		else if (left2 || midl2 || right2 || top2 || midlV2 || button2 || LDiagonal2 || RDiagonal2) {
			system("cls");
			cout << "\x1b[9" << theme << "m * * * * К О Н Е Ц  И Г Р Ы * * * * \x1bm\n\n";
			cout << "\x1b[9" << theme << "m         ВЫЙГРАЛ ИГРОК: " << name2 << "\x1bm\n";
			win = 2;
			cout << "\x1b[9" << theme << "mНажмите клавишу, чтобы продолжить: \x1bm";
			cin >> select;
			return 2;
		}
		else if (numberOfSteps == 9)
		{
			system("cls");
			cout << "\x1b[9" << theme << "m * * * * К О Н Е Ц  И Г Р Ы * * * * \x1bm\n";
			cout << "\x1b[9" << theme << "m           ! Н И Ч Ь Я !\x1bm\n";
			cout << "\x1b[9" << theme << "m!!! П О Б И Д И Л А  Д Р У Ж Б А !!!\x1bm\n\n";

			win = 3;
			cout << "\x1b[9" << theme << "mНажмите клавишу, чтобы продолжить: \x1bm";
			cin >> select;
			return 3;
		}
	}
}

int main() {
	system("cls");
	SetConsoleCP(1251);
	SetConsoleOutputCP(1251);
	//Переменные настроек
	string name;
	char figure;
	char color;
	char setings_player = '0';
	string name1 = "Игрок1";
	char figure1 = 'X';
	char color1 = '4';
	string name2 = "Игрок2";
	char figure2 = 'O';
	char color2 = '1';
	char theme = '3';
	char select = '0';
	int resPlay = 0, winP1 = 0, winP2 = 0, winC = 0, draw = 0;
	select = Menu(select, theme);



	while (select != '4')
	{
		switch (select)
		{
		case '1':
			select = MenuPlay(select, theme);
			while (select != '3')
			{
				switch (select)
				{
				case '1':
					resPlay = PlaySolo(select, name1, figure1, color1, figure2, theme);
					if (resPlay == 1)
					{
						winP1++;
					}
					else if (resPlay == 2)
					{
						winC++;
					}
					else
					{
						draw++;
					}
					break;
				case '2':
					resPlay = PlayDuo(select, name1, figure1, color1, name2, figure2, color2, theme);
					if (resPlay == 1)
					{
						winP1++;
					}
					else if (resPlay == 2)
					{
						winP2++;
					}
					else
					{
						draw++;
					}
				case '3':
					break;
				}
				select = MenuPlay(select, theme);
			}
			break;
		case '2':
			Statistics(select, resPlay, winP1, winP2, winC, draw, theme, name1, name2);
			break;
		case '3':
			select = Setings(theme);
			while (select != '4')
			{
				if (select == '3')
				{
					theme = SettingsOfTheme(theme);
				}
				else
				{
					setings_player = MenuSettingsOfPlayer(select, name1, name2, figure1, figure2, color1, color2, theme);
					while (setings_player != '4')
					{
						if (select == '1') {
							name = name1;
							figure = figure1;
							color = color1;
						}
						else {
							name = name2;
							figure = figure2;
							color = color2;
						}
						switch (setings_player)
						{
						case '1':
							name = SettingsOfNik(theme);
							break;
						case '2':
							figure = SettingsOfFigure(theme);
							break;
						case '3':
							color = SettingsOfColor(theme);
							break;
						default:
							break;
						}
						if (select == '1') {
							name1 = name;
							figure1 = figure;
							color1 = color;
						}
						else {
							name2 = name;
							figure2 = figure;
							color2 = color;
						}
						setings_player = MenuSettingsOfPlayer(select, name1, name2, figure1, figure2, color1, color2, theme);
					}
				}
				select = Setings(theme);
			}
			break;
		case '4':
			Exit(select, theme);
			break;
		default:
			cout << "\x1b[91m[+] Используйте указанные для навигации символы и цыфры!!\n\x1b[0m";
			//Sleep(3000);
			select = Menu(select, theme);
			break;
		}
		select = Menu(select, theme);
	}
	int _; cin >> _;
	return 0;
}