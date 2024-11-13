#include <iostream>
#include <fstream>
#include <string>

using namespace std;

// Функция для проверки файла на наличие вирусного образца
bool isVirus(const string& filename) {
    ifstream file(filename);
    string line;

    // Проверяем, есть ли строка с именем вируса в файле
    while (getline(file, line)) {
        if (line == "VirusName") { // Замените "VirusName" на фактическое имя вируса
            return true;
        }
    }

    return false;
}

int main() {
    string filename;

    cout << "Введите имя файла для проверки: ";
    cin >> filename;

    if (isVirus(filename)) {
        cout << "Файл " << filename << " заражен вирусом!" << endl;
        // Здесь можно добавить код для удаления или карантина файла
    } else {
        cout << "Файл " << filename << " чист." << endl;
    }

    return 0;
}
