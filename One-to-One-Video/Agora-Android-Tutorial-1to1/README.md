# Android 1-to-1 Tutorial

*English | [中文](README.zh.md)*

Real-time video chatting immerses people in the sights and sounds of human connections, keeping them engaged in your app longer.

Using this demo app, you can:

- Join and leave a channel
- Mute and unmute audio
- Switch camera on a mobile device
- Configure image resolution, frame rate, and bit rate

This page shows you how run high-quality, low-latency, real-time video calls, voice calls, and interactive broadcasting events in this Android demo app.

## Prerequisites

To follow this procedure you must have:

- A valid [Agora account](https://docs.agora.io/en/Agora%20Platform/sign_in_and_sign_up) and an [Agora project](https://docs.agora.io/en/Agora%20Platform/manage_projects?platform=All%20Platforms#create-a-new-project)
- [Java Development Kit](https://www.oracle.com/java/technologies/downloads/)
- Android Studio 3.3 or greater
- Two Android physical devices


Best practice is to test this demo app using a mobile device. Some simulators have missing functionality or lack the performance necessary to run this demo app


## Build this demo app in your local developer environment

To download and configure this demo app in your local developer environment:

1. **Download the demo app to your local machine**:

   In the terminal, clone this repository to `<install dir>` on your local device:
   ````bash
   cd <install dir>
   git clone git@github.com:AgoraIO/Basic-Video-Call.git
   ````
2. **Open the demo app in your developer IDE**:

   In Android Studio, open this demo app from:
    ````bash
    <install dir>/Basic-Video-Call/One-to-One-Video/Agora-Android-Tutorial-1to1
   ````
   You see the source files for this demo app in an Android view.


3. **Integrate Video SDK into the demo project**

   In `Gradle Scripts/build.gradle (Module: Agrora-Android-Tutorial-1to1.app)`, add the Video SDK implementation:
    ```
    dependencies {
      ...
      implementation 'io.agora.rtc:full-sdk:3.0.0'
    }
    ```
   Android Studio automatically syncs all dependencies. If you cannot access the implementation [install the sdk on your local machine](#reference).


4. **Create an authentication token**

   To ensure communication security, Agora uses tokens, that is, dynamic keys, to authenticate channel access. In Agora Console, [generate a temporary token](https://docs.agora.io/en/Agora%20Platform/get_appid_token?platform=All%20Platforms#generate-an-rtc-temporary-token).


5. **Add your token to the demo app**
    1. In Android Studio, open `app\res\values\strings.xml`.
    6. Update `<#YOUR APP ID#>` and `<#YOUR ACCESS TOKEN#>` with the temporary token `APP ID` and `Temp Token` you generated previously.

       ```xml
       <string name="agora_app_id"><#YOUR APP ID#></string>
       <!-- Obtain a temp Access Token at https://dashboard.agora.io -->
       <!-- You will need to deploy your own token server for production release -->
       <!-- Leave this value empty if Security keys/Token is not enabled for your project -->
       <string name="agora_access_token"><#YOUR TOKEN#></string>
       ```

6. **Build the demo app**

   In Android Studio, click **Build** > **Make Project**.

Your app is now compiled and ready to test.

## Test this demo

To try out Agora Video Call functionality on your mobile devices:

1. Connect your Android devices to your local development machine.
2. In Android Studio, in the toolbar, click the arrow next to the current device and click **Select multiple devices**.
3. In **Select multiple devices**, click the devices and click **OK**.

4. Click **Run** > **Run 'app'**.

A moment later you see the video call is opened on the demo app installed on your devices. You can talk to yourself using both devices. Why not lend one to a friend and talk to them?


## Next steps

- You use temporary tokens for testing only. In a production environment, best practice is to deploy a token server. See [Generate a Token](https://docs.agora.io/en/Interactive%20Broadcast/token_server?platform=Android) for more information.

- To see more tutorials, have a look at our [Agora SDK Samples](https://github.com/AgoraIO).
- For a more complete example, take a look at the [Agora use case](https://github.com/AgoraIO-usecase).
- Have a look at some apps made by the [Agora Community](https://github.com/AgoraIO-Community).
- You can find full API documentation in the [Document Center](https://docs.agora.io/en/).
- For potential issues, take a look at our [FAQ](https://docs.agora.io/en/faq).
- If you encounter problems during integration,  have a look in [Stack Overflow](https://stackoverflow.com/questions/tagged/agora.io).
- Not working for you? File an issue about this demo app in the [GitHub repo](https://github.com/AgoraIO/Basic-Video-Call/issues).


## Reference

If you cannot access the Agora Video Call implementation automatically, download it and add it to your project. To do this:

1. Unzip the Agora Video SDK from [Agora.io SDK](https://www.agora.io/en/download/) to a local directory.
3. Copy the following files from the **libs** folder of the SDK package to your Android project:

   Copy from SDK|Copy to Project Folder
      ---|---
   .jar file|**/apps/libs** folder
   **arm64-v8a** folder|**/app/src/main/jniLibs** folder
   **x86** folder|**/app/src/main/jniLibs** folder
   **armeabi-v7a** folder|**/app/src/main/jniLibs** folder



## License

The MIT License (MIT)
