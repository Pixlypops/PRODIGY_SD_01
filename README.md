# Temperature Conversion Program README

## Introduction

This program converts temperatures between Celsius, Fahrenheit, and Kelvin. The user inputs a temperature value along with its unit of measurement, and the program outputs the equivalent temperatures in the other two units.

## Features

- Convert Celsius to Fahrenheit and Kelvin.
- Convert Fahrenheit to Celsius and Kelvin.
- Convert Kelvin to Celsius and Fahrenheit.
- Handle invalid unit inputs gracefully.

## How to Use

1. **Input Prompt**: The program prompts you to enter a temperature value followed by its unit of measurement.
2. **Unit of Measurement**: 
    - 'C' for Celsius
    - 'F' for Fahrenheit
    - 'K' for Kelvin
3. **Output**: The program will display the temperature in the other two units of measurement.

## Example

- Input: `25 C`
- Output:
  ```
  The temperature in Fahrenheit is: 77°F
  The temperature in Kelvin is: 298.15K
  ```

## Code Breakdown

### Header Files
```cpp
#include <iostream>
#include <cctype>
using namespace std;
```
- `#include <iostream>`: Allows for input and output operations.
- `#include <cctype>`: Includes functions for character manipulation.

### Main Function
```cpp
int main() 
{
  // Prompt user for input
  cout << "Enter a temperature and the unit of measurement: ";
  double temp;
  char unit;
  cin >> temp >> unit;
  unit = tolower(unit); // Convert unit to lowercase for easy comparison
  double celsius, fahrenheit, kelvin;

  // Conversion logic based on the unit of measurement
  if (unit == 'c'){
    fahrenheit = (temp * 9/5) + 32;
    kelvin = temp + 273.15;
    cout << "\nThe temperature in Fahrenheit is: " << fahrenheit << "\u00B0F\n" << endl;
    cout << "The temperature in Kelvin is: " << kelvin << "\u00B0K\n" << endl;
  } else if (unit == 'f') {
    celsius = (temp - 32) * 5/9;
    kelvin = (temp - 32) * 5/9 + 273.15;
    cout << "\nThe temperature in Celsius is: " << celsius << "\u00B0C\n" << endl;
    cout << "The temperature in Kelvin is: " << kelvin << "\u00B0K\n" << endl;
  } else if (unit == 'k') {
    celsius = temp - 273.15;
    fahrenheit = (temp - 273.15) * 9/5 + 32;
    cout << "\nThe temperature in Celsius is: " << celsius << "\u00B0C\n" << endl;
    cout << "The temperature in Fahrenheit is: " << fahrenheit << "\u00B0F\n" << endl;
  } else {
    // Handle invalid unit input
    cout << "\nUnknown unit of measurement\nEnter 'C', 'F', or 'K'" << endl;
  }
}
```

### Key Sections

- **Input Handling**: 
  ```cpp
  cout << "Enter a temperature and the unit of measurement: ";
  double temp;
  char unit;
  cin >> temp >> unit;
  unit = tolower(unit);
  ```
  Prompts the user for temperature and unit, and converts the unit to lowercase.

- **Conversion Logic**: 
  ```cpp
  if (unit == 'c') { ... } else if (unit == 'f') { ... } else if (unit == 'k') { ... } else { ... }
  ```
  Converts the temperature based on the unit provided and outputs the results.

- **Output**:
  ```cpp
  cout << "\nThe temperature in Fahrenheit is: " << fahrenheit << "\u00B0F\n" << endl;
  cout << "The temperature in Kelvin is: " << kelvin << "\u00B0K\n" << endl;
  ```
  Displays the converted temperatures.

### Error Handling
If the user inputs an unknown unit, the program outputs an error message:
```cpp
cout << "\nUnknown unit of measurement\n Enter 'C', 'F', or 'K'" << endl;
```

## Compilation and Execution

1. **Compilation**: Compile the code using a C++ compiler.
   ```sh
   g++ -o temperature_converter temperature_converter.cpp
   ```
2. **Execution**: Run the compiled program.
   ```sh
   ./temperature_converter
   ```

Enjoy using the Temperature Conversion Program!
