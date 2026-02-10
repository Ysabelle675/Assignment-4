# Assignment-4
Assignment 4
Transcript link: https://share.google/aimode/H6ST8jkcVqRtnI0U3
Video link: https://www.canva.com/design/DAHAPnK3uD8/YiLtm6fWPrCPp7X8xx4saw/edit?utm_content=DAHAPnK3uD8&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton
Main.cpp link: https://replit.com/@ysanchez76/Assignment-4#main.cpp
:)
Code: #include <iostream>
#include <iomanip>

// Added: Function to calculate average
double calculateAverage(int sum, int size) {
    if (size == 0) return 0.0;
    return static_cast<double>(sum) / size; // cast to double to avoid integer division
}

int calculateSum(const int scores[], int size) {
    int sum = 0;
    for (int i = 0; i < size; i++) {
        sum += scores[i];
    }
    return sum;
}

void addBonus(int scores[], int size, int bonus) {
    for (int i = 0; i < size; i++) {
        scores[i] += bonus;
    }
}

int findMinimum(const int* scores, int size) {
    if (size <= 0) return 0;
    int min = *scores; 
    for (int i = 1; i < size; i++) {
        if (*(scores + i) < min) {
            min = *(scores + i);
        }
    }
    return min;
}

// Updated logic: matches the main() output requirement (>= 80)
int countHighPerformers(const int scores[], int size) {
    int count = 0;
    for (int i = 0; i < size; i++) {
        if (scores[i] >= 80) count++;
    }
    return count;
}

int main() {
    const int SIZE = 10;
    int ary[SIZE] = {82, 67, 69, 81, 68, 94, 74, 89, 37, 75};

    std::cout << "Original scores: ";
    for (int s : ary) std::cout << s << " ";
    std::cout << std::endl;

    int sum = calculateSum(ary, SIZE);
    double avg = calculateAverage(sum, SIZE);
    std::cout << "Sum: " << sum << std::endl;
    std::cout << "Average: " << std::fixed << std::setprecision(2) << avg << std::endl;

    int bonusValue = 10;
    addBonus(ary, SIZE, bonusValue);
    std::cout << "Scores after +" << bonusValue << " bonus: ";
    for (int i = 0; i < SIZE; i++) std::cout << ary[i] << " ";
    std::cout << std::endl;

    std::cout << "Minimum score: " << findMinimum(ary, SIZE) << std::endl;
    std::cout << "High performers (>=80): " << countHighPerformers(ary, SIZE) << std::endl;

    return 0;
}

