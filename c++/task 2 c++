#include <iostream>
#include <vector>
using namespace std;

struct Node {
    char data;
    Node* next;
    Node(char d) : data(d), next(nullptr) {}
};

bool hasDuplicates(Node* head) {
    Node* current = head;
    
    while (current != nullptr) {
        Node* runner = current->next;
        while (runner != nullptr) {
            if (current->data == runner->data) {
                return true; // Найден повторяющийся элемент
            }
            runner = runner->next;
        }
        current = current->next;
    }
    return false; // Повторов не найдено
}

int main() {
    // Создаем тестовый односвязный список: a -> b -> c -> a -> d
    Node* head = new Node('a');
    head->next = new Node('b');
    head->next->next = new Node('c');
    head->next->next->next = new Node('a'); // Повторяющийся элемент
    head->next->next->next->next = new Node('d');

    // Проверяем наличие повторов
    if (hasDuplicates(head)) {
        cout << "В списке есть повторяющиеся элементы" << endl;
    } else {
        cout << "В списке нет повторяющихся элементов" << endl;
    }

    // Очистка памяти
    Node* current = head;
    while (current != nullptr) {
        Node* temp = current;
        current = current->next;
        delete temp;
    }

    return 0;
}
