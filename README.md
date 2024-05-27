There is a live reload feature for capacitor.js framework. Still, there is no clear tutorial to use live reload on the capacitor angular app for Android using a physical device connected via USB. This tutorial will help you to connect live reload for the physical device (Works on Angular + Capacitor)
# Angular-Capacitor-live-reload-steps
Angular Capacitor js live reload for physical device
To enable live reload for an Angular Capacitor project with physical devices connected via USB, you can follow these steps:

1. **Set Up Your Environment:**
   - Ensure you have Node.js and npm installed.
   - Install Angular CLI and Capacitor CLI if you haven't already:

     npm install -g @angular/cli
     npm install -g @capacitor/cli

2. **Create or Navigate to Your Angular Project:**
   - If you don't have an Angular project yet, create one:

     ng new my-angular-app
     cd my-angular-app

   - If you already have a project, navigate to its root directory.

3. **Add Capacitor to Your Project:**
   - Initialize Capacitor:

     npx cap init

     Follow the prompts to set up Capacitor with your project.

4. **Install Necessary Plugins:**
   - Install Capacitor plugins for Android or iOS:

     npm install @capacitor/android
     npm install @capacitor/ios

5. **Build Your Angular Project:**
   - Run the Angular build command:

     ng build --watch

     This will start a build process that watches for changes and rebuilds the project automatically.

6. **Set Up Live Reload:**
   - Add the following to your `capacitor.config.json` to enable live reload:

    const config: CapacitorConfig = {
  appId: 'com.Chennaisuperkings.app',
  appName: 'CSK-new-ui',
  webDir: 'dist',
  server: {
    url: 'http://YOUR_LOCAL_IP:ANGULAR_PORT', DEFAULT 4200, if you are using different port set here
    cleartext: true
  }
};

     Replace `YOUR_LOCAL_IP` with your local IP address. You can find your local IP address by running `ifconfig` on macOS/Linux or `ipconfig` on Windows.

7. **Connect Your Device via USB:**
   - Ensure your Android or iOS device is connected via USB and developer mode is enabled.

8. **Run Capacitor Sync:**
   - Sync your project with Capacitor to update any changes:

     npx cap sync

9. **Run the Project on Your Device:**
   - For Android:

     npx cap open android

     Open Android Studio and run the project on your connected device.

   - For iOS:

     npx cap open ios

     Open Xcode and run the project on your connected device.

10. **Serve Your Angular Application:**
    - Start the Angular development server:

      ng serve --host 0.0.0.0 --port 4200

      This command starts the development server and makes it accessible over your local network.

Once these steps are completed, your Angular project should be live reloading on your physical device connected via USB. Any changes you make to your Angular code will automatically be reflected on the device.
