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
![LogIn Page](![image](https://github.com/user-attachments/assets/1a840f42-960f-4159-982b-5ca0a554c271)
)
![Register Page](![image](https://github.com/user-attachments/assets/4aa60f19-7c45-40cd-8726-3aa169b4cdac)
)
![Day View](![image](https://github.com/user-attachments/assets/2644369c-650a-4d11-890c-63f753bfe2a2)
)
![Calendar View](![image](https://github.com/user-attachments/assets/d2d28408-9b29-4d53-8788-a3a7a627d6eb)
)
![Profile View](![image](https://github.com/user-attachments/assets/6907599c-dd8e-4c74-aca8-b806f589b8d1)
)
![Accounts Settings View](![image](https://github.com/user-attachments/assets/bed07b00-d117-4d88-bf3c-a185f63da000)
)
![Task View](![image](https://github.com/user-attachments/assets/2b7dc656-2de9-44e7-8b99-f8e817e11772)
)
![Add Task View](![image](https://github.com/user-attachments/assets/406ab9de-5fa2-400d-bae6-b9648aef87a1)
)

## Video Demonstration
[![Watch the video](https://img.youtube.com/vi/KWuNdweHWtk/0.jpg)](https://youtu.be/KWuNdweHWtk)

# Acknowledgments
   - Thanks to Android Studio for providing a robust development environment.
   - Thanks to the open-source community for libraries like Retrofit, Hilt, and GSON that make development easier.
   - Thanks to the Android community for their continuous support and contributions.

