# iOS-freeRASP-React-Native-Bypass
Frida script to bypass freeRASP React Native for iOS apps ;P  
[ios-freerasp-react-native-bypass.js](ios-freerasp-react-native-bypass.js)
```
/*
    iOS freeRASP React Native Bypass by rodolfomarianocy
    frida -U -f <bundle_identifier> --codeshare rodolfomarianocy/ios-freerasp-react-native-bypass
    https://github.com/rodolfomarianocy/iOS-freeRASP-React-Native-Bypass
*/
console.warn("[+] iOS freeRASP React Native Bypass...")
if (ObjC.available) {
    try {
        Interceptor.replace(
            ObjC.classes.FreeraspReactNative['- talsecStart:withResolver:withRejecter:'].implementation,
            new NativeCallback(function() {}, 'void', [])
        );
    } catch (error) {
        console.log(error.message);
    }
} else {
    console.log("[-] ObjC Runtime unavailable");
}
```

-> mode of use
```
frida -U -f <bundle_identifier> --codeshare rodolfomarianocy/ios-freerasp-react-native-bypass
```
