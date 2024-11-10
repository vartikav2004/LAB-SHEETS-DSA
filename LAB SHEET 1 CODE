#include <iostream>
#include <string>
#include <unordered_map>
#define MAX_SIZE 100

// Class for Static Array Implementation
class StaticArray {
    int arr[MAX_SIZE]; // Static array with fixed size
    int size;

public:
    StaticArray() : size(0) {}

    // Insert element at specified index
    void insert(int element, int index) {
        if (size >= MAX_SIZE || index < 0 || index > size) {
            std::cout << "Insertion not possible." << std::endl;
            return;
        }
        for (int i = size; i > index; --i) {
            arr[i] = arr[i - 1];
        }
        arr[index] = element;
        size++;
    }

    // Remove element at specified index
    void remove(int index) {
        if (index < 0 || index >= size) {
            std::cout << "Deletion not possible." << std::endl;
            return;
        }
        for (int i = index; i < size - 1; ++i) {
            arr[i] = arr[i + 1];
        }
        size--;
    }

    // Traverse the static array
    void traverse() const {
        std::cout << "[";
        for (int i = 0; i < size; ++i) {
            std::cout << arr[i];
            if (i < size - 1) std::cout << ", ";
        }
        std::cout << "]" << std::endl;
    }
};

// Class for Dynamic Array Implementation
class DynamicArray {
    int *arr;      // Pointer to the dynamic array
    int size;      // Number of elements
    int capacity;  // Current capacity of the array

    // Resizes the array when capacity is reached
    void resize() {
        capacity *= 2;
        int *newArr = new int[capacity];
        for (int i = 0; i < size; ++i) {
            newArr[i] = arr[i];
        }
        delete[] arr;
        arr = newArr;
    }

public:
    DynamicArray() : size(0), capacity(2) {
        arr = new int[capacity];
    }

    ~DynamicArray() {
        delete[] arr;
    }

    // Insert element in the dynamic array
    void insert(int element) {
        if (size == capacity) {
            resize();
        }
        arr[size++] = element;
    }

    // Remove element at specified index
    void remove(int index) {
        if (index < 0 || index >= size) {
            std::cout << "Deletion not possible." << std::endl;
            return;
        }
        for (int i = index; i < size - 1; ++i) {
            arr[i] = arr[i + 1];
        }
        size--;
    }

    // Traverse the dynamic array
    void traverse() const {
        std::cout << "[";
        for (int i = 0; i < size; ++i) {
            std::cout << arr[i];
            if (i < size - 1) std::cout << ", ";
        }
        std::cout << "]" << std::endl;
    }
};

// Class for String Operations
class StringOperations {
public:
    // Concatenate two strings
    std::string concatenate(const std::string &str1, const std::string &str2) {
        return str1 + str2;
    }

    // Extract a substring from a given string
    std::string substring(const std::string &str, int start, int length) {
        if (start < 0 || start >= str.size() || start + length > str.size()) {
            return "";
        }
        return str.substr(start, length);
    }

    // Compare two strings lexicographically
    bool compare(const std::string &str1, const std::string &str2) {
        return str1 == str2;
    }
    
    // Count frequency of each character in a string
    std::unordered_map<char, int> characterFrequency(const std::string &str) {
        std::unordered_map<char, int> frequency;
        for (char c : str) {
            frequency[c]++;
        }
        return frequency;
    }
};

// Function to demonstrate the StringOperations class
void demonstrateStringOperations() {
    StringOperations so;
    std::string str1 = "hello";
    std::string str2 = "world";
    
    // Concatenate strings
    std::cout << "Concatenation: " << so.concatenate(str1, str2) << std::endl;
    // Extract a substring
    std::cout << "Substring: " << so.substring(str1, 3, 2) << std::endl;
    // Compare two strings
    std::cout << "Comparison: " << (so.compare(str1, str2) ? "True" : "False") << std::endl;
    
    // Calculate and print character frequency
    std::string testString = "hello";
    auto freq = so.characterFrequency(testString);
    std::cout << "Character Frequencies:" << std::endl;
    for (const auto &pair : freq) {
        std::cout << pair.first << ": " << pair.second << std::endl;
    }
}

// Main function demonstrating StaticArray, DynamicArray, and StringOperations
int main() {
    // Static Array test case
    std::cout << "Static Array Operations:" << std::endl;
    StaticArray staticArr;
    staticArr.insert(1, 0);
    staticArr.insert(2, 1);
    staticArr.remove(0);
    std::cout << "Expected Output: [2]" << std::endl;
    std::cout << "Desired Output: ";
    staticArr.traverse();

    // Dynamic Array test case
    std::cout << "\nDynamic Array Operations:" << std::endl;
    DynamicArray dynamicArr;
    dynamicArr.insert(1);
    dynamicArr.insert(2);
    dynamicArr.remove(0);
    std::cout << "Expected Output: [2]" << std::endl;
    std::cout << "Desired Output: ";
    dynamicArr.traverse();

    // String Operations test case
    std::cout << "\nString Operations:" << std::endl;
    demonstrateStringOperations();

    return 0;
}
