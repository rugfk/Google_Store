# 안드로이드 OS가 설치된 Tinker Edge R 보드에서 구글스토어 설치하는 방법 

***
* [0] SSH로 호스트컴퓨터에서 타겟보드 원격연결하기
```
ssh yourID@yourIP
```

* [1] 호스트컴퓨터에서 google_store.zip 파일 다운로드하기 
   [(https://drive.google.com/file/d/1iAdyCOLzXCDPegOUdGoOGGhjtqBa9yi5/view?usp=sharing)](https://drive.google.com/file/d/1iAdyCOLzXCDPegOUdGoOGGhjtqBa9yi5/view?usp=sharing)
  
* [2] 호스트컴퓨터에서 압축풀기
```
unzip google_store.zip
```

* [3] 'adb push'를 이용해서 압축푼 바이너리파일을 호스트컴퓨터에서 타겟보드에 전송하기
```
adb push "com.google.android.gms_21.21.16_(100400-378233385)-212116028_minAPI28(arm64-v8a,armeabi-v7a)(nodpi)_apkmirror.com.apk" /system/priv-apk
adb push "com.google.android.gsf.login_7.1.2-25_minAPI23(nodpi)_apkmirror.com.apk" /system/priv-apk
adb push "com.google.android.gsf_9-6794505-28_minAPI28(nodpi)_apkmirror.com.apk" /system/priv-apk
adb push "com.google.android.gms_21.21.16_(100400-378233385)-212116028_minAPI28(arm64-v8a,armeabi-v7a)(nodpi)_apkmirror.com.apk" /system/priv-apk
adb push "com.google.android.gms_21.21.16_(100400-378233385)-212116028_minAPI28(arm64-v8a,armeabi-v7a)(nodpi)_apkmirror.com.apk" /system/priv-apk
adb push "com.google.android.gsf.login_7.1.2-25_minAPI23(nodpi)_apkmirror.com.apk" /system/priv-apk
adb push "com.google.android.gsf_9-6794505-28_minAPI28(nodpi)_apkmirror.com.apk" /system/priv-apk

cd arm64-v8a

adb push "lib.bat" /system/lib
adb push "libgeller_jni_lite_lib.so" /system/lib
adb push "libmatching.so" /system/lib
adb push "libAppDataSearch.so" /system/lib
adb push "libgmscore.so" /system/lib
adb push "libsemanticlocation_inference_jni.so" /system/lib
adb push "libWhisper.so" /system/lib
adb push "libgoogle-ocrclient-v3.so" /system/lib
adb push "libsslwrapper_jni.so" /system/lib
adb push "libbrotli_native.so" /system/lib
adb push "libinertial-anchor-jni.so" /system/lib
adb push "libvcdiffjni.so" /system/lib
adb push "libconscrypt_gmscore_jni.so" /system/lib
adb push "libjgcastservice.so" /system/lib
adb push "libwearable-selector.so" /system/lib
adb push "libgcastv2_base.so" /system/lib
adb push "libjingle_peerconnection_so.so" /system/lib
adb push "libgcastv2_support.so" /system/lib
adb push "libleveldbjni.so" /system/lib

adb reboot
```


... 작 성 중 ....
