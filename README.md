# Android Simple Toast Library

This is a simple Android library that provides an easy way to display Toast messages.

## Features

*   `SimpleToast.showShortToast(Context context, String message)`: Displays a short duration Toast message.
*   `SimpleToast.showLongToast(Context context, String message)`: Displays a long duration Toast message.

## Installation (JitPack)

To use this library in your Android project, follow these steps:

1.  **Add JitPack repository to your root `build.gradle`**:

    ```gradle
    allprojects {
        repositories {
            google()
            mavenCentral()
            maven { url 'https://jitpack.io' }
        }
    }
    ```

2.  **Add the dependency to your app module's `build.gradle`**:

    ```gradle
    dependencies {
        implementation 'com.github.YOUR_GITHUB_USERNAME:android-toast-library:1.0.0'
    }
    ```

    **Important**: Replace `YOUR_GITHUB_USERNAME` with your actual GitHub username and `1.0.0` with the desired version tag.

## Usage

```java
import com.example.toastlibrary.SimpleToast;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        Button shortToastButton = findViewById(R.id.shortToastButton);
        shortToastButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                SimpleToast.showShortToast(MainActivity.this, "This is a short toast!");
            }
        });

        Button longToastButton = findViewById(R.id.longToastButton);
        longToastButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                SimpleToast.showLongToast(MainActivity.this, "This is a long toast message.");
            }
        });
    }
}
```

## Publishing to JitPack

1.  **Upload your project to GitHub**: Create a new public GitHub repository and push this entire `android-toast-library` project to it.

2.  **Create a Release**: Go to your GitHub repository, navigate to "Releases" and create a new release with a tag (e.g., `1.0.0`). The tag name should match the `version` specified in your `toastlibrary/build.gradle` file.

3.  **JitPack Build**: Visit [JitPack.io](https://jitpack.io/), paste your GitHub repository URL, and click "Look up". JitPack will then attempt to build your library. If the build is successful, you will see the instructions to include the library in your project.

## Project Structure

```
android-toast-library/
├── build.gradle
├── settings.gradle
└── toastlibrary/
    ├── build.gradle
    └── src/
        └── main/
            └── java/
                └── com/
                    └── example/
                        └── toastlibrary/
                            └── SimpleToast.java
```

**Note**: Remember to replace `YOUR_GITHUB_USERNAME` in `toastlibrary/build.gradle` and in the `implementation` line of your app's `build.gradle` with your actual GitHub username before publishing.
