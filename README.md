#include <Windows.h>
#include <iostream> 
#include <string>                          // Подключение строк
#include <cstdlib>
#include <ctime>                           // Работа с временем 
#include <thread>

using namespace std;                       // Подключение std пространства для сокращения кода
using namespace std::chrono_literals;

void calculator();                         // Калькулятор 
void timee();                              // Дата-время
void game();                               // игра // нихуя не понял 
int recyrsia(int d);                       // Рекурсия стек 
int factorial(int i);                      // Факториал числа



int main() {                               // Начало выбор функции 
	setlocale(LC_ALL, "RU");
	srand(time(NULL));                     // Генерация случайных чисел 





	
	int da = 1;
	while (da == 1) {                      // Цикл запуска программы 
		cout << "############################################################" << endl << endl;
		cout << "Открыть программу?" << endl << "1 - Да" << " " << "2 - Нет" << endl;
		cin >> da;

		if (da == 2) {     
			cout << "Bye-bye!" << endl;    // Выход из цикла
			break; 
		}

		if (da == 1){                      // Выполнить цикл 
			cout << "############################################################" << endl << endl;
			cout << "Приветствую,выберете функцию:" << endl << "1 - Калькулятор. " << endl << "2 - Точное время. " << endl << "3 - Игра. " << endl << "4 - Дз. " << endl;
			cout << "Введите цифру функции: ";
			int k;
			cin >> k;

			switch (k){                    // Выбор действия через оператор switch 
			  case 1: calculator();               // Вызов функции
				break;
			  case 2: timee();             // Вызов функции
				break;
			  case 3: game();
				break;
			  case 4:                     
				  while (4) {              // Дополнительное миню
					  int i;
					  cout << "Выбюор примера дз:" << endl << "1 - Пример рекурсии и стека. " << endl << "2 - Факториал числа: " << endl;
					  cin >> i;
						  if (i == 1) {
							  recyrsia(5);   
							  break;
						  }
					      if (i == 2) {
							  cout << "Из числа:" << endl;
								  cin >> i;
								  factorial(i);                                  // Вызов функции
								  cout << "Ответ: " << factorial(i) << endl;     // Вывод результата процесса функции
							  break;
						  }
						  break;
				  }
			   break;
			 
			  default: cout << "Ошибка 505";         // Если ни одно из условий не верно то default 
				
			}
		}
	}
	return 0;
}




void calculator() {    // Калькулятор 

	float a, b, c;                             // Создание переменных float типа (целые числа и с запятой)
	char t;                                    // Создание переменной char тиа (знак) 
	cout << "############################################################" << endl << endl;
	cout << "Введите первое число:";
	cin >> a;
	cout << "Введите знак:";
	cin >> t;
	cout << "Введите второе число:";
	cin >> b;

	switch (t) {                               // Проверка на совпадение условий

	  case '-': cout << "Ответ:" << (a - b) << endl; // Вычитание
		break;

	  case '+': cout << "Ответ:" << (a + b) << endl; // Сложение
		break;

	  case '*': cout << "Ответ:" <<(a * b) << endl;  // Умножение
		break;

	  case '/': cout << "Ответ:" << (a / b) << endl; // Деление
		break;

       default: cout << "Ошибка 505" << endl;    // Оштбка ввода char переменной
	}
}

void timee() {    // Дата-время
	SYSTEMTIME st;
	GetLocalTime(&st);
	cout << "############################################################" << endl << endl;
	cout << "Точное время: " << endl << st.wDay << "." << st.wMonth << "." << st.wYear << endl << st.wHour << "час" << "." << st.wMinute << "мин" << endl << endl << endl;
	cout << "############################################################" << endl << endl;
}

void game() {   // игра // нихуя не понял 

	srand(time(0));

	while (true)
	{
		cout << "================================================================================ \n";
		cout << " \nИгра \nКамень Ножницы Бумага \nГотовы играть?  " << endl << "1 - да " << "0 - Выход " << ":";
		int piayerInput = 0;
		cin >> piayerInput;
		if (piayerInput == 0) {

			break;
		}


		int counter = 0;
		while (counter < 3)
		{
			cout << counter << "\n";
			counter = counter + 1;
			this_thread::sleep_for(1s);
		}

		int random_value = rand();
		random_value = random_value % 3;

		if (random_value == 0)
		{
			cout << "Камень!\n";
		}
		if (random_value == 1)
		{
			cout << "Бумага!\n";
		}
		if (random_value == 2)
		{
			cout << "Ножницы!\n";
		}


	}
	cout << "Bye-bye!";
}

int recyrsia(int d) {         // Рекурсия - вызов функии самой себя 
	if (d < 1)                 // Цыкл будет работать до того как int будет меньше 1 и будем возвращать 0 . выход из рекурсии 
		return 0;
	d--;                          // Отнимаеи от переменной -1 с кадым проходом цыкла
	cout << d << endl;            // выводим переменную на экран 
	return recyrsia(d);           // Возврат функии самой себя где переменная инт -1
}

int factorial(int i) {       // Факториал числа 

	if (i == 0)               
		return 0;
	if (i == 1)
		return 1;

	return i * factorial(i - 1);
}
