# Dart Isolates for Parallel API Calls - Demo

This repository provides a demonstration of how to use Dart Isolates for performing parallel API calls. It showcases how to effectively offload data fetching tasks (e.g., fetching user data, employee data, family data, etc.) to separate Isolates, preventing UI blocks and improving performance, especially in Flutter applications.

## Table of Contents
- [Introduction](#introduction)
- [Features](#features)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [API Services](#api-services)
- [Contributing](#contributing)
- [License](#license)

## Introduction

Dart Isolates allow you to run multiple tasks in parallel, making them useful for scenarios where you need to execute long-running or CPU-intensive operations without blocking the main thread. This project demonstrates the use of Dart Isolates to fetch various data sets concurrently. The example simulates API data fetching for users, employees, family, relatives, and students.

## Features

- **Parallel data fetching**: Uses Dart Isolates to fetch data from multiple "API services" concurrently.
- **Non-blocking**: Keeps the main thread responsive, useful in Flutter apps to avoid UI freezing.
- **Modular structure**: Clear separation of concerns, with each data type (user, employee, family, etc.) handled separately.

## Prerequisites

Before you can run the project, ensure that you have the following installed on your system:

- Dart SDK (>=2.12.0)
- Flutter (if using this in a Flutter project)

## Installation

1. **Clone the Repository**

   ```bash
   git clone https://github.com/risfat/Dart_Isolates_for_Parallel_API_Calls-Demo.git
   cd Dart_Isolates_for_Parallel_API_Calls-Demo
   ```

2. **Install Dependencies**

   If you are using Flutter:

   ```bash
   flutter pub get
   ```

   For Dart:

   ```bash
   dart pub get
   ```

## Usage

To see the demo in action, you can run the Dart code in your terminal or integrate it into your Flutter app.

### Running the Dart script

If this is a standalone Dart project:

```bash
dart run main.dart
```

### Running in a Flutter Project

If you are integrating this into a Flutter app, just call the `getAllIsolatesData()` function from your UI or business logic layer to fetch all the data sets in parallel.

### Example

```dart
void fetchData() async {
  ApiServices apiServices = ApiServices();
  List<dynamic> allData = await apiServices.getAllIsolatesData();
  print(allData);
}
```

## Project Structure

```
lib/
│
├── dummy_json/
│   ├── employee_data_json.dart
│   ├── family_data_json.dart
│   ├── relative_data_json.dart
│   ├── student_data_json.dart
│   └── user_data_json.dart
│
├── models/
│   └── person_model.dart
│
├── api_services.dart     # Contains the Isolate logic and API service methods
└── main.dart             # Entry point for the demo
```

### Explanation

- `dummy_json/`: Contains JSON data used to simulate API responses.
- `models/`: Contains the `PersonModel` class, which maps the JSON data into Dart objects.
- `api_services.dart`: The core logic that demonstrates how Dart Isolates can be used to make parallel API calls.
- `main.dart`: A sample entry point that triggers the isolate-based data fetching.

## API Services

The following data sets are fetched concurrently in the demo:

- **User Data**
- **Employee Data**
- **Family Data**
- **Relative Data**
- **Student Data**

These data sets are simulated through predefined JSON objects, which can be found in the `dummy_json/` directory.

## Contributing

Feel free to submit issues or pull requests if you want to contribute to this demonstration project. Any feedback and contributions are welcome!

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Open a Pull Request

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

Happy coding! If you have any questions or suggestions, feel free to open an issue in the repository.