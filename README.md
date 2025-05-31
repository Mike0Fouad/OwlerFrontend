# Owler's Frontend

A Java based Calendar Application that connects to the Flask Backend, providing a seamless user experience for managing events and tasks.

## Features

- **Task Management** Backup and syncing the tasks and edit them.
- **Display Calendar** View the calendar.
- **Account Management** Create and manage user accounts.

## Technologies Used

- **Java** (Main programming language)
- **Android Studio** (IDE for Android Development)
- **XML** (For UI Layouts)
- **Retrofit** (For API calls)
- **Hilt** (Dependency Injection)
- **GSON** (Data format for API responses and Storage)


## Installation

### Prerequisites

- Java 11 or higher
- Android Studio
- Android SDK
- Gradle
- An emulator or physical device for testing (optional)
- Server Link 
- Ngrok Link (optional, for exposing the server to the internet)


## Setup Instructions

1. **Download the Repository**:
    Clone the repository or download it as a ZIP file and extract it.

2. **Open in Android Studio**:
    - Open Android Studio.
    - Select "Open an existing Android Studio project".
    - Navigate to the cloned repository and select it.

3. **Configure the Project**:
    - Open the `build.gradle` file in the root directory.
    - Ensure that the `minSdkVersion` and `targetSdkVersion` are set according to your requirements.
    - Sync the project with Gradle files.

4. **Set Up Dependencies**:
    - Open the `build.gradle` file in the `app` directory.
    - Ensure that the necessary dependencies for Retrofit, Hilt, and GSON are included etc.
    - Sync the project again.
    
5. **Configure API Endpoints**:
    - Navigate to `app\build.gradle`.
    - Set the `BASE_URL` to your Flask backend URL in BuildConfig's `BASE_URL` variables.

6. **Testing Without Server (Optional)**:
    - Navigate to `\app\src\main\java\com\owlerdev\owler\ui\activity\LauncherActivity.java`.

    - Modify The following Codes:
    ```java
      protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);

        String token = tokenManager.getAccessToken();

        // Check if the token is null, empty, or expired
        Intent intent;
        if (token == null || token.isEmpty() || isTokenExpired(token)) {
            // Redirect to AuthActivity if no token or token is invalid/expired
            intent = new Intent(this, AuthActivity.class);
        } else {
            // Redirect to MainActivity (or ProfileFragment directly depending on the flow)
            intent = new Intent(this, MainActivity.class);
        }

        startActivity(intent);
        finish(); // Prevent going back to LauncherActivity
    }
    ```

    To:
    ```java
      protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);

        // Redirect to MainActivity directly for testing without server
        Intent intent = new Intent(this, MainActivity.class);
        startActivity(intent);
        finish(); // Prevent going back to LauncherActivity
    }
    ```
    

7. **Run the Application**:
    - Connect an Android device or start an emulator.
    - Click on the "Run" button in Android Studio.
    - Select the device/emulator you want to run the app on.
    - Wait for the app to build and install.

8. **APK Generation**:
    - To generate an APK, go to `Build` > `Build Bundle(s)/APK(s)` > `Build APK(s)`.
    - The generated APK will be located in the `app/build/outputs/apk/debug` directory.

## Snapshots
![LogIn Page]()
![Register Page]()
![Day View]()
![Calendar View]()
![Profile View]()
![Accounts Settings View]()
![Task View]()
![Add Task View]()

## Video Demonstration
[![Watch the video](https://img.youtube.com/vi/KWuNdweHWtk/0.jpg)](https://youtu.be/KWuNdweHWtk)

# Acknowledgments

   - Thanks to the open-source community for providing libraries and tools that made this project possible.
