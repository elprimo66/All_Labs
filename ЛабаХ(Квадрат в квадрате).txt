#include <iostream>

using namespace std;


int main() {
	setlocale(0, "");

	int select;
	int length;
	//length2 для фигур с разными гранями
	int length2;
	char texture;
	int i = 1;
	int col = 2;

	cout << "\x1b[96mПрограмма - “Геометрические фигуры\x1b[0m" << endl;
	cout << endl;

	cout << "\x1b[93m[1] Линия\x1b[0m" << endl;
	cout << "\x1b[93m[2] Квадрат\x1b[0m" << endl;
	cout << "\x1b[93m[3] Прямоугольник\x1b[0m" << endl;
	cout << "\x1b[93m[4] Треугольник\x1b[0m" << endl;
	cout << "\x1b[93m[5] Решетка\x1b[0m" << endl;
	cout << "\x1b[93m[6] Крестик\x1b[0m" << endl;
	cout << "\x1b[93m[7] Плюс\x1b[0m" << endl;
	cout << "\x1b[93m[8] Ромб\x1b[0m" << endl;
	cout << "\x1b[93m[9] Квадрат в квадрате, в квадрате...\x1b[0m" << endl;
	cout << endl;

	cout << "\x1b[92mВыберите фигуру: \x1b[0m";
	cin >> select;
	cout << endl;

	//Обработка выбора фигуры ЛИНИЯ
	if (select == 1) {
		system("cls");

		cout << "\x1b[92mВыбрана фигура: Линия\x1b[0m" << endl;
		cout << endl;
		cout << "\x1b[93m[1]Горизонтальная\x1b[0m" << endl;
		cout << "\x1b[93m[2]Вертикальная\x1b[0m" << endl;
		cout << endl;
		cout << "\x1b[92mВыберите тип: \x1b[0m";

		cin >> select;
		cout << endl;

		cout << "\x1b[92mВыберите длинну: \x1b[0m";
		cin >> length;
		cout << endl;

		cout << "\x1b[92mВыберите текстуру: \x1b[0m";
		cin >> texture;

		switch (select)
		{
			// Горизонтальная линия
		case 1:
			cout << " ";
			while (i <= length)
			{
				i++;
				cout << "\x1b[95m" << texture << "\x1b[0m";
			}
			return 0;
			break;
			// Вертикальная линия
		case 2:
			while (i <= length)
			{
				i++;
				cout << "\x1b[95m" << " " << texture << "\x1b[0m" << endl;
			}
			return 0;
			break;
		default:
			break;
		}


		return 0;
	}
	//Обработка выбора фигуры КВАДРАТ
	else if (select == 2) {
		cout << "\x1b[92mВыбрана фигура: Квадрат\x1b[0m" << endl;
		cout << endl;
		cout << "\x1b[93m[1] Заполненный\x1b[0m" << endl;
		cout << "\x1b[93m[2] Пустой\x1b[0m" << endl;
		cout << endl;
		cout << "\x1b[92mВыберите тип: \x1b[0m";

		cin >> select;
		cout << endl;

		cout << "\x1b[92mВыберите длинну грани: \x1b[0m";
		cin >> length;
		cout << endl;

		cout << "\x1b[92mВыберите текстуру: \x1b[0m";
		cin >> texture;

		switch (select)
		{
			//Заполненый квадрат
		case 1:
			for (int i = 1; i <= length; i++)
			{
				for (int i2 = 1; i2 <= length; i2++)
				{
					cout << "\x1b[95m" << texture << "  " << "\x1b[0m";
				}
				cout << endl;
			}
			return 0;
			break;
			//Пустой квадрат
		case 2:
			for (int i = 0; i < length; i++)
			{
				cout << texture << " ";
			}
			cout << endl;
			for (int i = 0; i < length - 2; i++)
			{
				cout << texture << " ";
				for (size_t i2 = 0; i2 < length - 2; i2++)
				{
					cout << "  ";
				}
				cout << texture << " ";
				cout << endl;
			}
			for (int i = 0; i < length; i++)
			{
				cout << texture << " ";
			}
			cout << endl;
			return 0;
			break;
		default:
			break;
		}
		return 0;
	}
	//Обработка выбора фигуры Прямоушольник
	else if (select == 3) {
		cout << "\x1b[92mВыбрана фигура: Прямоушольник\x1b[0m" << endl;
		cout << endl;
		cout << "\x1b[93m[1] Заполненный\x1b[0m" << endl;
		cout << "\x1b[93m[2] Пустой\x1b[0m" << endl;
		cout << endl;
		cout << "\x1b[92mВыберите тип: \x1b[0m";

		cin >> select;
		cout << endl;

		cout << "\x1b[92mВыберите длинну горизонтальной грани: \x1b[0m";
		cin >> length;
		cout << endl;

		cout << "\x1b[92mВыберите длинну вортикальной грани: \x1b[0m";
		cin >> length2;
		cout << endl;

		cout << "\x1b[92mВыберите текстуру: \x1b[0m";
		cin >> texture;

		switch (select)
		{
			//Заполненый прямоугольник
		case 1:
			for (int i = 1; i <= length; i++)
			{
				for (int i2 = 1; i2 <= length; i2++)
				{
					cout << "\x1b[95m" << texture << "  " << "\x1b[0m";
				}
				cout << endl;
			}
			return 0;
			break;
			//Пустой прямоугольник
		case 2:
			for (int i = 0; i < length; i++)
			{
				cout << "\x1b[95m" << texture << "  " << "\x1b[0m";
			}
			cout << endl;
			for (int i2 = 0; i2 < length2 - 2; i2++)
			{
				cout << "\x1b[95m" << texture << "\x1b[0m";
				for (int i3 = 0; i3 < length * 3 - 4; i3++)
				{
					cout << " ";
				}
				cout << "\x1b[95m" << texture << "\x1b[0m";
				cout << endl;
			}
			for (int i = 0; i < length; i++)
			{
				cout << "\x1b[95m" << texture << "  " << "\x1b[0m";
			}
			return 0;
			break;
		default:
			break;
		}
		return 0;
	}
	//Обработка выбора фигуры Треугольник
	else if (select == 4) {
		cout << "\x1b[92mВыбрана фигура: Треугольник\x1b[0m" << endl;
		cout << endl;
		cout << "\x1b[93m[1] Заполненный\x1b[0m" << endl;
		cout << "\x1b[93m[2] Пустой\x1b[0m" << endl;
		cout << endl;
		cout << "\x1b[92mВыберите тип: \x1b[0m";

		cin >> select;
		cout << endl;

		cout << "\x1b[92mВыберите длинну горизонтальной грани: \x1b[0m";
		cin >> length;
		cout << endl;

		cout << "\x1b[92mВыберите текстуру: \x1b[0m";
		cin >> texture;

		//Заполненый треугольник
		if (select == 1) {
			for (int y = 0; y < length / 2 + 1; y++)
			{
				for (int x = 0; x < length; x++)
				{
					if (length / 2 - y <= x && length / 2 + y >= x && y <= length / 2) {
						cout << texture << " ";
					}
					else {
						cout << ". ";
					}
				}
				cout << endl;
			}
		}
		//Пустой треугольник
		else if (select == 2) {
			for (int y = 0; y < length / 2 + 1; y++)
			{
				for (int x = 0; x < length; x++)
				{
					if (length / 2 - y == x || length / 2 + y == x || y == length / 2) {
						cout << texture << " ";
					}
					else {
						cout << ". ";
					}
				}
				cout << endl;
			}
		}
	}
	//Обработка выбора фигуры Решетка
	else if (select == 5) {
		cout << "\x1b[92mВыбрана фигура: Решетка\x1b[0m" << endl;
		cout << endl;

		cout << "\x1b[92mВыберите размер: \x1b[0m";
		cin >> length;
		cout << endl;

		cout << "\x1b[92mВыберите текстуру: \x1b[0m";
		cin >> texture;


		for (int y = 0; y < length; y++)
		{
			for (int x = 0; x < length; x++)
			{
				if (x % 2 != 0 || y % 2 != 0) {
					cout << texture << " ";
				}
				else {
					cout << ". ";
				}
			}
			cout << endl;
		}
	}
	//Обработка выбора фигуры Крестик
	else if (select == 6) {
		cout << "\x1b[92mВыбрана фигура: Крестик\x1b[0m" << endl;
		cout << endl;

		cout << "\x1b[92mВыберите размер: \x1b[0m";
		cin >> length;
		cout << endl;

		cout << "\x1b[92mВыберите текстуру: \x1b[0m";
		cin >> texture;

		for (int y = -length / 2; y < length / 2 + 1; y++)
		{
			for (int x = 0; x < length; x++)
			{
				if (length / 2 - y == x || length / 2 + y == x) {
					cout << texture << " ";
				}
				else {
					cout << ". ";
				}
			}
			cout << endl;
		}
	}
	//Обработка выбора фигуры Плюс
	else if (select == 7) {
		cout << "\x1b[92mВыбрана фигура: Плюс\x1b[0m" << endl;
		cout << endl;

		cout << "\x1b[92mВыберите размер: \x1b[0m";
		cin >> length;
		cout << endl;

		cout << "\x1b[92mВыберите текстуру: \x1b[0m";
		cin >> texture;

		for (int y = 0; y < length; y++)
		{
			for (int x = 0; x < length; x++)
			{
				if (length / 2 == x || length / 2 == y) {
					cout << texture << " ";
				}
				else {
					cout << ". ";
				}
			}
			cout << endl;
		}
	}
	//Обработка выбора фигуры Ромб
	else if (select == 8) {
		cout << "\x1b[92mВыбрана фигура: Ромб\x1b[0m" << endl;
		cout << endl;

		cout << "\x1b[92mВыберите размер: \x1b[0m";
		cin >> length;
		cout << endl;

		cout << "\x1b[92mВыберите текстуру: \x1b[0m";
		cin >> texture;

		for (int y = 0; y < length; y++)
		{
			for (int x = 0; x < length; x++)
			{
				if (length / 2 - y == x || length / 2 + y == x || length / 2 + y - length + 1 == x || length / 2 - y + length - 1 == x) {
					cout << texture << " ";
				}
				else {
					cout << ". ";
				}
			}
			cout << endl;
		}
	}
	//Обработка выбора фигуры квадрат в квадрате
	else if (select == 9) {
		cout << "\x1b[92mВыбрана фигура: Квадрат в квадрате\x1b[0m" << endl;
		cout << endl;
		cout << endl;

		cout << "\x1b[92mВыберите размер: \x1b[0m";
		cin >> length;
		cout << endl;

		cout << "\x1b[92mВыберите текстуру: \x1b[0m";
		cin >> texture;

		for (int y = 0; y < length; y++) {		
			for (int x = 0; x < length; x++) {
				bool top = y % 2 == 0 && x >= y && length - y > x;
				bool left = x % 2 == 0 && y >= x && length - x > y;
				bool right = x % 2 == 0 && y <= x && length - x < y + 2;
				bool button = y % 2 == 0 && x <= y && length - y < x + 2;
				if (button  || right || left || top) {
					cout << texture << " ";
				}
				else {
					cout << ". ";
				}
			}
			cout << endl;
		}
	}
	//Обработка неправильного выбора
	else {
		cout << "\x1b[91mОшибка! Используйте указанные в меню цифры для навигации!!\x1b[0m" << endl;
		return 0;
	}
	cout << "[0] Выход в меню ";
	cin >> select;

	while (select != 0) {
		cout << "\x1b[91mОшибка! Используйте указанные в меню цифры для навигации!!\x1b[0m" << endl;
		cin >> select;
		if (select == 0) {
			system("cls");
			main();
		}
	}
	return 0;
}
