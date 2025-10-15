
Click windows button + X

Go to System > Advanced system settings

You will be guided to a log-in page, here add Username as .\LocalAdmin and the password you can find if you open local admin manager and select show password (take a screen shot/photo as it can't be copied)

Once through this point another modal should appear, here follow the steps below

Set the PATH (could be any variable name here) Environment Variable:

Now, you need to set the PATH environment variable to point to the JDK installation directory:

- Right-click on the Windows icon in the taskbar and select “System.”
- In the System window, click on “Advanced system settings” on the left sidebar.

In the System Properties window, click the “Environment Variables” button.

- In the Environment Variables window, under the “System variables” section, click “New.”
- For the “Variable name,” enter PATH.
- For the “Variable value,” enter the path to your directory.
- Click “OK” to save the variable.


Issues with PATH in VS Code

This issue might be due to the fact that Visual Studio Code is not recognizing the system PATH variable where Vue CLI is installed. Here's how you can fix it:

1. Open a new command prompt (not from VS Code) and type `where vue`. This should return the path where Vue CLI is installed.
    
2. Copy this path.
    
3. In VS Code, go to File > Preferences > Settings (or press `Ctrl+,`).
    
4. Search for `terminal.integrated.env.windows` in the search bar.
    
5. Click on "Edit in settings.json".
    
6. In the settings.json file, you should see a JSON object that looks like this:
    

"terminal.integrated.env.windows": {}

7. Modify this object to include the PATH variable, like so:

"terminal.integrated.env.windows": {

    "PATH": "<your-path>"

}

ie   "terminal.integrated.env.windows": {

    "PATH": "${env:PATH};C:\\Users\\ArajarDW\\AppData\\Roaming\\npm"

  }

Replace `<your-path>` with the path you copied in step 2. Make sure to include `${env:PATH};` at the beginning to include the existing PATH variables.

8. Save the settings.json file and restart VS Code.

Now, the integrated terminal in VS Code should recognize the `vue` command.

