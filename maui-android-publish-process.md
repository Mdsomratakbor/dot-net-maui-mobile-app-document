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

	What is your first and last name? 
	[Unknown]: John Doe

	What is the name of your organizational unit? 
	[Unknown]: Development

	What is the name of your organization? 
	[Unknown]: MyCompany

	What is the name of your city or locality? 
	[Unknown]: New York

	What is the name of your state or province? 
	[Unknown]: NY

	What is the two-letter country code for this unit? 
	[Unknown]: US

	Is CN=John Doe, OU=Development, O=MyCompany, L=New York, ST=NY, C=US correct? 
	[no]: yes
	
	Enter key password for <mykey> (RETURN if same as keystore password): 

## Step 2: Configure the .NET MAUI Project

1. **Open your .NET MAUI project in your preferred IDE (e.g., Visual Studio).**

2. **Locate and open your project file (e.g., `.csproj`).**

3. **Add the following property group to configure the keystore properties:**

```xml
<PropertyGroup Condition="$(TargetFramework.Contains('-android')) and '$(Configuration)' == 'Release'">
  <AndroidKeyStore>True</AndroidKeyStore>
  <AndroidSigningKeyStore>petadoption.app.keystore</AndroidSigningKeyStore>
  <AndroidSigningKeyAlias>key</AndroidSigningKeyAlias>
  <AndroidSigningKeyPass></AndroidSigningKeyPass>
  <AndroidSigningStorePass></AndroidSigningStorePass>
</PropertyGroup>
4. **Replace the placeholder values:**
1. petadoption.app.keystore: The path to your keystore file.
2. key: The alias for the key (as specified during the keystore creation).
3. AndroidSigningKeyPass: The password for the key.
4. AndroidSigningStorePass: The password for the keystone.
