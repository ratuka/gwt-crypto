# Code #

This code below assumes a constant key.  Note that this is not very secure.  Consider using TripleDesKeyGenerator in a more sophisticated fashion.

```
TripleDesCipher cipher = new TripleDesCipher();
cipher.setKey(GWT_DES_KEY);
try {
  enc = cipher.encrypt(String.valueOf(value));
} catch (DataLengthException e1) {
  e1.printStackTrace();
} catch (IllegalStateException e1) {
  e1.printStackTrace();
} catch (InvalidCipherTextException e1) {
  e1.printStackTrace();
}
```

On the client, make sure you inherit the module:
`<inherits name='com.googlecode.gwt.crypto.Crypto'/>`
Then:

```
TripleDesCipher cipher = new TripleDesCipher();
cipher.setKey(GWT_DES_KEY);
String dec ="";
try {
  dec = cipher.decrypt(enc);
} catch (DataLengthException e) {
  e.printStackTrace();
} catch (IllegalStateException e) {
  e.printStackTrace();
} catch (InvalidCipherTextException e) {
  e.printStackTrace();
}
```

# Install #

Declare the module
```
<inherits name="com.googlecode.gwt.crypto.Crypto"/> 
```

## Maven ##

### Starting with gwt-crypto 2.3.0 ###
```
<dependencies>
    <dependency>
        <groupId>com.googlecode.gwt-crypto</groupId>
        <artifactId>gwt-crypto</artifactId>
        <version>2.3.0</version>
    </dependency>
</dependencies>
```

### Before gwt-crypto 2.3.0 ###
First add the repo to your repo list:
```
<repositories>
    <repository>
        <id>gwt-crypto repo</id>
        <url>http://gwt-crypto.googlecode.com/svn/trunk/repo/</url>
     </repository>
</repositories>
```

Then add the dependency:
```
<dependencies>
    <dependency>
        <groupId>com.googlecode.gwt.crypto</groupId>
        <artifactId>gwt-crypto</artifactId>
        <version>1.0.2</version>
    </dependency>
</dependencies>
```

## non-Maven Usage ##

Non-Maven users can download the jar from the download tab and deploy it in whatever format you have defined.