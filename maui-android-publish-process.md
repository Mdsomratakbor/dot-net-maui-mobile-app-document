# .NET MAUI Application Release Documentation

This guide provides step-by-step instructions to create a keystore, configure your .NET MAUI project for signing, and publish the application.

## Step 1: Generate a Keystore

1. **Open a terminal or command prompt.**

2. **Execute the following command to generate a keystore file:**
   ```sh
   keytool -genkey -v -keystore keystore-file-name -alias key -keyalg RSA -keysize 2048 -validity 10000
3. **Enter the required details when prompted:**
  ```sh
	Enter keystore password: 
	Re-enter new password:

