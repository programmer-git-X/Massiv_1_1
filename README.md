## ПРОГРАММИРОВАНИЕ УСЛОВНЫХ ОПЕРАТОРОВ И  ЦИКЛИЧЕСКИХ ВЫЧИСЛИТЕЛЬНЫХ ПРОЦЕССОВ
## _Цель работы_ : освоение методов организации циклических программ сложной структуры.

#### Задан массив  действительных чисел Х. Определить процент положительных, отрицательных и нулевых элементов массива А.

## Программа
    #include <iostream>
    #include <conio.h>
    
    #define N 10
    
    //Генерирует случайное число в заданном диапазоне
    float generate_random_float(float min_value, float max_value) {
        float random_value = (float)rand() / RAND_MAX; // Генерация случайного значения от 0 до 1
        float range = max_value - min_value; // Определение диапазона
        return (random_value * range) + min_value; // Приведение к нужному диапазону
    }
    
    int main()
    {
        setlocale(LC_ALL, "Rus");
        srand(time(NULL)); // Инициализация генератора случайных чисел
    
        float X[N];
        int positiveCount = 0;
        int negativeCount = 0;
        int zeroCount = 0;
    
        //Заполняем массив данными
        for (int i = 0; i < N; i++) {
            X[i] = generate_random_float(-100, 100);
            printf("X[%d] = %.3f\n", i, X[i]);
        }
    
        for (int i = 0; i < N; i++) {
            if (X[i] > 0)
                positiveCount++;
            else if (X[i] < 0)
                negativeCount++;
            else
                zeroCount++;
        }
    
        float positivePercentage = (float)positiveCount / N * 100;
        float negativePercentage = (float)negativeCount / N * 100;
        float zeroPercentage = (float)zeroCount / N * 100;
    
        printf("Процент положительных элементов: %.2f%%\n", positivePercentage);
        printf("Процент отрицательных элементов: %.2f%%\n", negativePercentage);
        printf("Процент нулевых элементов: %.2f%%\n", zeroPercentage);
        
        _getch();
    
        return 0;
    }

### Результат выполнения программы
![image](https://github.com/programmer-git-X/Massiv_1_1/assets/156421821/fb94634d-4d7e-46b7-86eb-108015386ce7)
