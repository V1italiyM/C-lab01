# C#-lab01 Виталий Михайлов ИУ8-31
## Цели работы:
  1. Научиться работать с переменными разных типов данных CTS средствами языка C#.
  2. Научиться создавать классы и поля классов, инициализировать свойства классов. Научиться создавать перегруженные конструкторы классов.
  3. Научиться создавать тесты для реализованных методов и классов.

## Задание №1
Выведите на консоль минимальные и максимальные значения для предопределенных типов данных CTS.

## Задание №2
Создайте класс с именем Rectangle.
В теле класса создайте два поля, описывающие длины сторон double sideA, sideB.
Создайте пользовательский конструктор Rectangle(double sideA, double sideB), в теле которого поля sideA и sideB инициализируются значениями аргументов.
Создайте два private метода, вычисляющие площадь прямоугольника - double CalculateArea() и периметр прямоугольника - double CalculatePerimeter ().
Создайте два свойства double Area и double Perimeter с одним методом доступа get, вызывающим созданные ранее методы.
Напишите программу, которая принимает от пользователя длины двух сторон прямоугольника и выводит на экран периметр и площадь. Покройте тестами методы класса Rectangle.

## Задание №3
Создайте классы Point и Figure.
Класс Point должен содержать два целочисленных поля с координатами точки.
Создайте два свойства с одним методом доступа get.
Создайте пользовательский конструктор, в теле которого проинициализируйте поля значениями аргументов.
Класс Figure должен содержать конструкторы, которые принимают от 3-х до 5-ти аргументов типа Point, а также строковое автосвойство для хранения названия фигуры. Используйте ключевое слово this для вызова перегруженных конструкторов, избегайте дублирования кода.
Создайте два метода: double LengthSide(Point A, Point B), который рассчитывает длину стороны многоугольника; double PerimeterCalculator(), который рассчитывает периметр многоугольника.
Напишите программу, которая выводит на экран название и периметр многоугольника. Покройте тестами методы класса Figure.

## Код задания № 1
Console.WriteLine("\t \t Минимальные и максимальные значения предопределенных типов данных CTS:");
Console.WriteLine("=========================================================");

// Целочисленные типы данных
Console.WriteLine("Целочисленные типы данных:");
Console.WriteLine($"byte: min = {byte.MinValue}, max = {byte.MaxValue}");
Console.WriteLine($"sbyte: min = {sbyte.MinValue}, max = {sbyte.MaxValue}");
Console.WriteLine($"short: min = {short.MinValue}, max = {short.MaxValue}");
Console.WriteLine($"ushort: min = {ushort.MinValue}, max = {ushort.MaxValue}");
Console.WriteLine($"int: min = {int.MinValue}, max = {int.MaxValue}");
Console.WriteLine($"uint: min = {uint.MinValue}, max = {uint.MaxValue}");
Console.WriteLine($"long: min = {long.MinValue}, max = {long.MaxValue}");
Console.WriteLine($"ulong: min = {ulong.MinValue}, max = {ulong.MaxValue}");
Console.WriteLine("=========================================================");

// Типы данных с плавающей точкой
Console.WriteLine("Типы данных с плавающей точкой:");
Console.WriteLine($"float: min = {float.MinValue}, max = {float.MaxValue}");
Console.WriteLine($"double: min = {double.MinValue}, max = {double.MaxValue}");
Console.WriteLine($"decimal: min = {decimal.MinValue}, max = {decimal.MaxValue}");
Console.WriteLine("=========================================================");

// Логический тип данных
Console.WriteLine("Логический тип данных:");
Console.WriteLine($"bool: true / false");
Console.WriteLine("=========================================================");

// Символьный тип данных
Console.WriteLine("Символьный тип данных:");
Console.WriteLine($"char: min = {char.MinValue}, max = {char.MaxValue}");
Console.WriteLine("=========================================================");

// Структуры
Console.WriteLine("Структуры:");
Console.WriteLine($"DateTime: min = {DateTime.MinValue}, max = {DateTime.MaxValue}");
Console.WriteLine($"TimeSpan: min = {TimeSpan.MinValue}, max = {TimeSpan.MaxValue}");
Console.WriteLine("=========================================================");

// Тип значений null
Console.WriteLine("Тип значений null:");
Console.WriteLine($"Nullable<T>: null");
Console.WriteLine("=========================================================");

## Код задания № 2
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Xml.Linq;

// Объявление пространства имен для проекта
namespace lab01_2
{
    public class Rectangle
    {
        // Поля для сторон прямоугольника
        private double sideA;
        private double sideB;

        // Конструктор
        public Rectangle(double sideA, double sideB)
        {
            this.sideA = sideA;
            this.sideB = sideB;
        }

        // Свойства для получения сторон
        public double SideA
        {
            get { return sideA; }
        }

        public double SideB
        {
            get { return sideB; }
        }

        // Свойство для площади
        public double Area
        {
            get { return sideA * sideB; }
        }

        // Свойство для периметра
        public double Perimeter
        {
            get { return 2 * (sideA + sideB); }
        }
    }

    // Основной класс программы
    class MyProgram
    {
        // Точка входа в программу
        static void Main()
        {
            // Запрос у пользователя длины первой стороны прямоугольника
            Console.Write("Первая сторона прямоугольника: ");
            double sideA = Convert.ToDouble(Console.ReadLine());

            // Запрос у пользователя длины второй стороны прямоугольника
            Console.Write("Вторая сторона прямоугольника: ");
            double sideB = Convert.ToDouble(Console.ReadLine());

            // Создание экземпляра класса Rectangle с введенными сторонами
            Rectangle rectangle = new Rectangle(sideA, sideB);

            // Вывод информации о прямоугольнике
            Console.WriteLine($"Введён прямоугольник со сторонами: {rectangle.SideA} и {rectangle.SideB}");
            Console.WriteLine($"Площадь прямоугольника: {rectangle.Area}");
            Console.WriteLine($"Периметр прямоугольника: {rectangle.Perimeter}");
        }
    }
}








C# lab01
