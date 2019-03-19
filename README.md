//# STL.-VECTOR.-.
//vector | Библиотека стандартных шаблонов (stl). Обучение С++
#include<iostream
#include<vector>
  using namespace std;
int main()
{
	setlocale(LC_ALL, "ru");
	/*vector<int> myVector;*///1й способ иниц-ции
	/*vector<int> myVector(20);*///2-й способ, при нем в () м. указать кол-во элементов,
	//которые б. в векторе, это не капасити, а реальные ячсейки, т е size
	 myVector(20,55) тогда выведется цифра 55 двадцать раз в консоли
	vector<int> myVector = { 0,22,78,99 };//еще один способ иниц-ции как в масиве работает
	myVector.reserve(100);//м. изначально под capacity,те под максимально применимый размер памяти
	//на случай добавления еще эл-в, выделить резерв в вектор :на100ячеек
	myVector.push_back(2);//метод, добавл-й эл-т в конец массива. Вектор-это объект класса, у него есть методы через точку
	myVector.push_back(44); 
	myVector.push_back(77);
	myVector.push_back(9);


	myVector[0] = 1000;//поместили в ячейку 0, другое значение
	cout << "количество элементов в векторе " << myVector.size() << endl;//рез-т 4
	//метод возвращ-т кол=-во элементов в векторе, не н. отдельная перем size
	for (int i = 0; i < myVector.size(); i++)
	{
		cout << myVector[i] << endl;//вывод эл-в
	}
	
	cout << myVector.at(1) << endl;//данный методat аналогичен [], т е позволяет получить доступ к элементам
	//рез-т: 44


	try
	{
		cout << myVector.at(10) << endl;
	}
	catch (const std::out_of_range & ex)
	{
		cout << ex.what() << endl << endl;//рез-т: invalid vector<T> subscript
	}
//мы м. с помощью try отловить исключение, что случилось при попытке обратиться к 
	//эл-ту большего размера чем в. с помощью out_of_range(при выходе за границы)



	//////////////другние методы вектора//////////////////
	myVector.pop_back();//удаляет последний элемент
	cout << "Использовали метод pop_back" <<   endl;
	for (int i = 0; i < myVector.size(); i++)
	{
		cout << myVector[i] << endl;//вывод эл-в
	}

	cout << "количество элементов в векторе " << myVector.size() << endl;
	myVector.clear();//очистить ветор от всенх элементов
	cout << "clear() количество элементов в векторе " << myVector.size() << endl;

	myVector.push_back(2);//метод, добавл-й эл-т в конец массива. Вектор-это объект класса, у него есть методу через точку
	myVector.push_back(44);
	myVector.push_back(77);
	myVector.push_back(9);
	cout << "capacity()  количество элементов в векторе //" << myVector.capacity() << endl;
	myVector.capacity();//выделяет доп память на всякий случай
	myVector.shrink_to_fit();//чтобы не терять лишней памяти, которую не сипоьзовали
	//под капасити, воспольз-ся этим методом, т е убрать неиспользов-ю память
	cout << "Использовали метод shrink_to_fit()" << endl;
	cout << "capacity()  количество элементов в векторе " << myVector.capacity() << endl;
	cout << "есть ли эл-ты в нашем векторе "<<myVector.empty() << endl;//проверка, есть ли эл-ты в нашем векторе
	//вернулся 0, значит, ложь, т е не пустой
	myVector.resize(27);//задали новый размер вектору
	//если resize(27,448) то появится двадцать семь чисел 448 значение в векторе
	cout << "resize количество элементов в векторе " << myVector.capacity() << endl;

	 


	return 0;
}
