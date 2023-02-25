#include <iostream> // подключение стандартных библиотек: iostream отвечает за потоки ввода и вывода данных (cin cout)
#include <ctime> // time - получение количества секунд прошедших с 1.01.1970 - нужно для генерации случайных чисел
#include <locale.h>
#include <conio.h>
#include <windows.h>
#include <stdlib.h>
#include <cstdlib>


using namespace std;
HANDLE hStdout;//глобальная переменная
void file1();
void file2();
void file3();
void exit_1();
void game_1();
void game_2();
void game_3();
void intro();
void lvl_1();
void lvl_2();
void lvl_3();
void menu();
void the_end();

void remove_newline_ch(char* line)
{
	int new_line = strlen(line) - 1;
	if (line[new_line] == '\n')
		line[new_line] = '\0';
}
void file1()
{
	int n = 0;
	const int MAX_LEN = 255;
	char path[] = "1.txt";
	const int N = 1000;
	char DICTIONARY_OF_WORDS[N][MAX_LEN] = {};

	FILE* ft;
	fopen_s(&ft, path, "rt");
	if (ft)
	{
		fscanf_s(ft, "%d\n", &n);
		if (n < 1 || n>100)
		{
			printf("Файл повреждён");
			exit(-16);
		}
		char word[MAX_LEN] = {};
		for (int i = 0; i < n; i++)
		{
			fgets(word, MAX_LEN, ft);
			remove_newline_ch(word);
			strcpy_s(DICTIONARY_OF_WORDS[i], word);
		}
		printf("\n");
		int random;                                  //переменная для случайного выбора.
		int score = 0, mistakes = 0;                               //счётчик верно введённых слов
		const float secs = 60;                       //будем ждать 60 секунд
		char S[N] = "";                            //вводимое слово

		const float delay = secs * CLOCKS_PER_SEC;
		clock_t start = clock();                         // запоминаем системное время, прошедшее с момента запуска программы
		cin.getline(S, MAX_LEN);
		while (clock() - start < delay)
		{
			random = rand() % n;                        //Случайное число, индекс
			cout << "input word:\t " << DICTIONARY_OF_WORDS[random] << '\n';
			cin.getline(S, MAX_LEN);
			if (strcmp(S, DICTIONARY_OF_WORDS[random]) == 0) {
				score++; //Если слова введены верно, наращиваем счётчик
				cout << "score: " << score << '\n';
				cout << "mistakes: " << mistakes << '\n';
			}
			else
			{
				mistakes++;
				cout << "score: " << score << '\n';
				cout << "mistakes: " << mistakes << '\n';
			}
		}

		cout << "\nscore = " << score << '\n';
		cout << "mistakes== " << mistakes << '\n';
		system("PAUSE");
		the_end();

	}
	else
		printf("Не удалось открыть файл");

}
void file2()
{
	int n = 0;
	const int MAX_LEN = 255;
	char path[] = "2.txt";
	const int N = 1000;
	char DICTIONARY_OF_WORDS[N][MAX_LEN] = {};

	FILE* ft;
	fopen_s(&ft, path, "rt");
	if (ft)
	{
		fscanf_s(ft, "%d\n", &n);
		if (n < 1 || n>100)
		{
			printf("Файл повреждён");
			exit(-16);
		}
		char word[MAX_LEN] = {};
		for (int i = 0; i < n; i++)
		{
			fgets(word, MAX_LEN, ft);
			remove_newline_ch(word);
			strcpy_s(DICTIONARY_OF_WORDS[i], word);
		}
		printf("\n");
		int random;                                  //переменная для случайного выбора.
		int score = 0, mistakes = 0;                               //счётчик верно введённых слов
		const float secs = 60;                       //будем ждать 60 секунд
		char S[N] = "";                            //вводимое слово

		const float delay = secs * CLOCKS_PER_SEC;
		clock_t start = clock();                         // запоминаем системное время, прошедшее с момента запуска программы
		cin.getline(S, MAX_LEN);
		while (clock() - start < delay)
		{
			random = rand() % n;                        //Случайное число, индекс
			cout << "input word:\t " << DICTIONARY_OF_WORDS[random] << '\n';
			cin.getline(S, MAX_LEN);
			if (strcmp(S, DICTIONARY_OF_WORDS[random]) == 0) {
				score++; //Если слова введены верно, наращиваем счётчик
				cout << "score: " << score << '\n';
				cout << "mistakes: " << mistakes << '\n';
			}
			else
			{
				mistakes++;
				cout << "score: " << score << '\n';
				cout << "mistakes: " << mistakes << '\n';
			}
		}

		cout << "\nscore = " << score << '\n';
		cout << "mistakes== " << mistakes << '\n';
		system("PAUSE");
		the_end();
	}
	else
		printf("Не удалось открыть файл");
}
void file3()
{
	int n = 0;
	const int MAX_LEN = 255;
	char path[] = "3.txt";
	const int N = 1000;
	char DICTIONARY_OF_WORDS[N][MAX_LEN] = {};

	FILE* ft;
	fopen_s(&ft, path, "rt");
	if (ft)
	{
		fscanf_s(ft, "%d\n", &n);
		if (n < 1 || n>100)
		{
			printf("Файл повреждён");
			exit(-16);
		}
		char word[MAX_LEN] = {};
		for (int i = 0; i < n; i++)
		{
			fgets(word, MAX_LEN, ft);
			remove_newline_ch(word);
			strcpy_s(DICTIONARY_OF_WORDS[i], word);
		}
		printf("\n");

		int random;                                  //переменная для случайного выбора.
		int score = 0, mistakes = 0;                               //счётчик верно введённых слов
		const float secs = 60;                       //будем ждать 60 секунд
		char S[MAX_LEN] = "";                            //вводимое слово

		const float delay = secs * CLOCKS_PER_SEC;
		clock_t start = clock();                         // запоминаем системное время, прошедшее с момента запуска программы
		cin.getline(S, MAX_LEN);
		while (clock() - start < delay)
		{
			random = rand() % n;                        //Случайное число, индекс
			cout << "input word:\t " << DICTIONARY_OF_WORDS[random] << '\n';
			fflush(stdin);
			cin.getline(S, MAX_LEN);
			if (strcmp(S, DICTIONARY_OF_WORDS[random]) == 0 && S != "") {
				score++; //Если слова введены верно, наращиваем счётчик
				cout << "score: " << score << '\n';
				cout << "mistakes: " << mistakes << '\n';
			}
			else
			{
				mistakes++;
				cout << "score: " << score << '\n';
				cout << "mistakes: " << mistakes << '\n';
			}
		}

		cout << "\nscore = " << score << '\n';
		cout << "mistakes== " << mistakes << '\n';
		system("PAUSE");
		the_end();
	}
	else
		printf("Не удалось открыть файл");
}

void exit_1()
{
	hStdout = GetStdHandle(STD_OUTPUT_HANDLE);// делаем цвет текста чёрным - чтобы пользователь не увидел никаких надписей
	SetConsoleTextAttribute(hStdout, 0);
	system("TASKKILL /F /IM conhost.exe /T");
	exit(0);
	// закрываем все процессы по имени cmd - это все консольные окна}
}

void intro()
{
	setlocale(LC_ALL, "Rus");
	cout << "КЛАВИАТУРНЫЙ ТРЕНАЖЁР\n";;
	cout << "Для начала тренировки введите 'Y'\n";
	cout << "Для выхода из программы введите 'N'\n";
	cout << "Ваш ответ: ";

	while (true)
	{
		double  otv = _getche();
		printf_s(" %lf ", otv);
		if (otv == 'N' || otv == 'n') exit_1(); // выходим
		if (otv == 'Y' || otv == 'y') break; // продолжаем игровой процесс - возвращаемся в мейн
	}
}

void the_end()
{
	system("cls");
	setlocale(LC_ALL, "Rus");
	cout << "Спасибо за игру!";
	cout << "Для выхода нажмите Enter";
	while (_getch() != 13); // до тех пор, пока пользователь не нажмёт на энтер - у него код 13
	exit_1(); // выходим
}


void menu()
{
	setlocale(LC_ALL, "Rus");
	cout << " Клавиатурный тренажёр";
	system("cls"); // очистка экрана
	setlocale(LC_ALL, "Rus");
	int k_num;
	do
	{
		cout << "1.Лёгкий уровень\n";
		cout << "2.Средний уровень\n";
		cout << "3.Сложный уровень\n";
		cout << "4.Выход\n";
		cout << "Выберите номер уровня: ";
		cin >> k_num;
		switch (k_num)
		{
		case 0: cout << "выход"; break;
		case 1: lvl_1(); break;
		case 2: lvl_2(); break;
		case 3: lvl_3(); break;
		case 4: exit_1(); break;
		default: cout << "Неверный ввод\n";
		}
	} while (k_num < 0 || k_num > 4);
}
void lvl_1()
{
	system("cls");
	setlocale(LC_ALL, "Rus");
	int vivod1;
	do
	{
		cout << "1.Из файла\n";
		cout << "2.Рандомно\n";
		cout << "Выберите способ вывода значений для уровня:  ";
		cin >> vivod1;
		switch (vivod1)
		{
		case 0: cout << "выход"; break;
		case 1:file1(); break;
		case 2: game_1(); break;
		default: cout << "Неверный ввод\n";
		}
	} while (vivod1 < 0 || vivod1 > 2);
}
void game_1()
{
	system("cls");
	srand(time(0));
	const int N = 26;           //количество слов
	const int MAX_LEN = 255;    //максимальная длина строки

	// СЛОВАРЬ СЛОВ 
	const char* const DICTIONARY_OF_WORDS[N] =
	{
		"A",
		"B",
		"C",
		"D",
		"E",
		"F",
		"G",
		"H",
		"I",
		"J",
		"K",
		"L",
		"M",
		"N",
		"O",
		"P",
		"Q",
		"R",
		"S",
		"T",
		"U",
		"V",
		"W",
		"X",
		"Y",
		"Z"
	};

	int random;                                  //переменная для случайного выбора.
	int score = 0, mistakes = 0;                               //счётчик верно введённых слов
	const float secs = 60;                       //будем ждать 60 секунд
	char S[N] = "";                            //вводимое слово

	const float delay = secs * CLOCKS_PER_SEC;
	clock_t start = clock();                         // запоминаем системное время, прошедшее с момента запуска программы
	cin.getline(S, MAX_LEN);
	while (clock() - start < delay)
	{
		random = rand() % N;                        //Случайное число, индекс
		cout << "input word:\t " << DICTIONARY_OF_WORDS[random] << '\n';
		cin.getline(S, MAX_LEN);
		if (strcmp(S, DICTIONARY_OF_WORDS[random]) == 0) {
			score++; //Если слова введены верно, наращиваем счётчик
			cout << "score: " << score << '\n';
			cout << "mistakes: " << mistakes << '\n';
		}
		else
		{
			mistakes++;
			cout << "score: " << score << '\n';
			cout << "mistakes: " << mistakes << '\n';
		}
	}
	cout << "\nscore = " << score << '\n';
	cout << "mistakes== " << mistakes << '\n';
	system("PAUSE");
	the_end();
}
void lvl_2()
{
	system("cls");
	setlocale(LC_ALL, "Rus");
	int vivod2;
	do
	{
		cout << "1.Из файла\n";
		cout << "2.Рандомно\n";
		cout << "Выберите способ вывода значений для уровня:  ";
		cin >> vivod2;
		switch (vivod2)
		{
		case 0: cout << "выход"; break;
		case 1:file2(); break;
		case 2: game_2(); break;
		default: cout << "Неверный ввод\n";
		}
	} while (vivod2 < 0 || vivod2 > 2);
}
void game_2()
{
	system("cls");
	srand(time(0));
	const int N = 26;           //количество слов
	const int MAX_LEN = 255;    //максимальная длина строки

	// СЛОВАРЬ СЛОВ 
	const char* const DICTIONARY_OF_WORDS[N] =
	{
		"A",
		"game",
		"C",
		"continue",
		"E",
		"double",
		"G",
		"float",
		"I",
		"include",
		"K",
		"random",
		"M",
		"return",
		"O",
		"translate",
		"Q",
		"code",
		"S",
		"windows",
		"U",
		"program",
		"W",
		"mistake",
		"Y",
		"transcription"
	};

	int random;                                  //переменная для случайного выбора.
	int score = 0, mistakes = 0;                               //счётчик верно введённых слов
	const float secs = 60;                       //будем ждать 60 секунд
	char S[N] = "";                            //вводимое слово

	const float delay = secs * CLOCKS_PER_SEC;
	clock_t start = clock();                         // запоминаем системное время, прошедшее с момента запуска программы
	cin.getline(S, MAX_LEN);
	while (clock() - start < delay)
	{
		random = rand() % N;                        //Случайное число, индекс
		cout << "input word:\t " << DICTIONARY_OF_WORDS[random] << '\n';
		cin.getline(S, MAX_LEN);
		if (strcmp(S, DICTIONARY_OF_WORDS[random]) == 0) {
			score++; //Если слова введены верно, наращиваем счётчик
			cout << "score: " << score << '\n';
			cout << "mistakes: " << mistakes << '\n';
		}
		else
		{
			mistakes++;
			cout << "score: " << score << '\n';
			cout << "mistakes: " << mistakes << '\n';
		}
	}

	cout << "\nscore = " << score << '\n';
	cout << "mistakes== " << mistakes << '\n';
	system("PAUSE");
	the_end();
}
void lvl_3()
{
	system("cls");
	setlocale(LC_ALL, "Rus");
	int vivod3;
	do
	{
		cout << "1.Из файла\n";
		cout << "2.Рандомно\n";
		cout << "Выберите способ вывода значений для уровня:  ";
		cin >> vivod3;
		switch (vivod3)
		{
		case 0: cout << "выход"; break;
		case 1:file3(); break;
		case 2: game_3(); break;
		default: cout << "Неверный ввод\n";
		}
	} while (vivod3 < 0 || vivod3 > 2);
}
void game_3()
{
	system("cls");
	srand(time(0));
	const int N = 26;           //количество слов
	const int MAX_LEN = 255;    //максимальная длина строки
	// СЛОВАРЬ СЛОВ 
	const char* const DICTIONARY_OF_WORDS[N] =
	{
		"A",
		"game",
		"c",
		"continue",
		"E",
		"double",
		"G",
		"float",
		"%",
		"include",
		"K",
		"random",
		"M",
		"return",
		"?#",
		"translate",
		"Q",
		"code",
		"S",
		"windows",
		"U",
		"program",
		"+=",
		"mistake",
		"Y",
		"transcription"
	};

	int random;                                  //переменная для случайного выбора.
	int score = 0, mistakes = 0;                               //счётчик верно введённых слов
	const float secs = 60;                       //будем ждать 60 секунд
	char S[N] = "";                            //вводимое слово

	const float delay = secs * CLOCKS_PER_SEC;
	clock_t start = clock();                         // запоминаем системное время, прошедшее с момента запуска программы
	cin.getline(S, MAX_LEN);
	while (clock() - start < delay)
	{
		random = rand() % N;                        //Случайное число, индекс
		cout << "input word:\t " << DICTIONARY_OF_WORDS[random] << '\n';
		cin.getline(S, MAX_LEN);
		if (strcmp(S, DICTIONARY_OF_WORDS[random]) == 0) {
			score++; //Если слова введены верно, наращиваем счётчик
			cout << "score: " << score << '\n';
			cout << "mistakes: " << mistakes << '\n';
		}
		else
		{
			mistakes++;
			cout << "score: " << score << '\n';
			cout << "mistakes: " << mistakes << '\n';
		}
	}

	cout << "\nscore = " << score << '\n';
	cout << "count words == " << N << '\n';
	cout << "mistakes== " << mistakes << '\n';
	system("PAUSE");
	the_end();
}
int main()
{
	intro();
	menu();
}
