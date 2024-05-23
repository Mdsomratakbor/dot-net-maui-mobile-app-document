
### Add the key store property on the mobile app project file
<pre>
  <PropertyGroup Condition="$(TargetFramework.Contains('-android')) and '$(Configuration)' == 'Release'">
	<AndroidKeyStore>True</AndroidKeyStore>
	<AndroidSigningKeyStore>petadoption.app.keystore</AndroidSigningKeyStore>
	<AndroidSigningKeyAlias>key</AndroidSigningKeyAlias>
	<AndroidSigningKeyPass></AndroidSigningKeyPass>
	<AndroidSigningStorePass></AndroidSigningStorePass>
</PropertyGroup>
</pre>
### Publish command
<pre>
  dotnet publish -f:version -c:Release /p:AndroidSigningKeyPass=password /p:AndroidSigningStorePass=password
</pre>
