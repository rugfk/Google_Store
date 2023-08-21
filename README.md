# 안드로이드 OS가 설치된 Tinker Edge R 보드에서 구글스토어 설치하는 방법 

***
* [1] 호스트컴퓨터와 안드로이드 타겟보드가 잘연결되었는지 확인하기 
```
adb devices

List of devices attached
D4JHGWI642	device
```

* [2] adb root를 입력하여 android에 root 권한을 줍니다 
```
adb root
restarting adbd as root
```

* [3] adb remount를 입력하여 system partition에 쓰기
권한을 줍니다.
```
adb remount
remount succeeded
```

* [4] 호스트컴퓨터에서 google_store.zip 파일 다운로드하기 
   [(https://drive.google.com/file/d/1iAdyCOLzXCDPegOUdGoOGGhjtqBa9yi5/view?usp=sharing)](https://drive.google.com/file/d/1iAdyCOLzXCDPegOUdGoOGGhjtqBa9yi5/view?usp=sharing)
  
* [5] 호스트컴퓨터에서 압축풀기
```
unzip google_store.zip
```

* [6] 'adb push'를 이용해서 압축푼 바이너리파일을 호스트컴퓨터에서 타겟보드에 전송하기
```
cd google_store

adb push "apk.bat" /system/priv-app
adb push "com.android.vending_25.9.19-21_0_PR_380694501-82591910_minAPI21(arm64-v8a,armeabi-v7a,x86,x86_64)(nodpi)_apkmirror.com.apk" /system/priv-app
adb push "com.google.android.gms_21.21.16_(100400-378233385)-212116028_minAPI28(arm64-v8a,armeabi-v7a)(nodpi)_apkmirror.com.apk" /system/priv-app
adb push "com.google.android.gsf.login_7.1.2-25_minAPI23(nodpi)_apkmirror.com.apk" /system/priv-app
adb push "com.google.android.gsf_9-6794505-28_minAPI28(nodpi)_apkmirror.com.apk" /system/priv-app

cd arm64-v8a

adb push "lib.bat" /system/lib
adb push "libAppDataSearch.so" /system/lib
adb push "libWhisper.so" /system/lib
adb push "libbrotli_native.so" /system/lib
adb push "libconscrypt_gmscore_jni.so" /system/lib
adb push "libgcastv2_base.so" /system/lib
adb push "libgcastv2_support.so" /system/lib
adb push "libgeller_jni_lite_lib.so" /system/lib
adb push "libgmscore.so" /system/lib
adb push "libgoogle-ocrclient-v3.so" /system/lib
adb push "libinertial-anchor-jni.so" /system/lib
adb push "libjgcastservice.so" /system/lib
adb push "libjingle_peerconnection_so.so" /system/lib
adb push "libleveldbjni.so" /system/lib
adb push "libmatching.so" /system/lib
adb push "libsemanticlocation_inference_jni.so" /system/lib
adb push "libsslwrapper_jni.so" /system/lib
adb push "libvcdiffjni.so" /system/lib
adb push "libwearable-selector.so" /system/lib
```

[7] adb shell을 이용하여 파일이 잘
설치 되어있는지 확인을 합니다.
```
adb shell
cd /system/priv-app
ls

cd /system/lib
ls

exit
```

[8] 타겟보드(안드로이드)를 재부팅합니다.

