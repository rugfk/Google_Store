# 안드로이드 OS가 설치된 Tinker Edge R 보드에서 구글스토어 설치하는 방법 

***
* [0] SSH로 호스트컴퓨터에서 타겟보드 원격연결하기
```
ssh yourID@yourIP
```

* [1] 호스트컴퓨터에서 google_store.zip 파일 다운로드하기 
  - [클릭하기(https://drive.google.com/file/d/1iAdyCOLzXCDPegOUdGoOGGhjtqBa9yi5/view?usp=sharing)](https://drive.google.com/file/d/1iAdyCOLzXCDPegOUdGoOGGhjtqBa9yi5/view?usp=sharing)
  
* [2] 호스트컴퓨터에서 압축풀기
```
unzip google_store.zip
```

* [3] 'adb push'를 이용해서 압축푼 바이너리파일을 호스트컴퓨터에서 타겟보드에 전송하기
```
adb push "com.google.android.gms_21.21.16_(100400-378233385)-212116028_minAPI28(arm64-v8a,armeabi-v7a)(nodpi)_apkmirror.com.apk" /system/priv-ab
adb push "com.google.android.gsf.login_7.1.2-25_minAPI23(nodpi)_apkmirror.com.apk" /system/priv-apk
```

... 작 성 중 ....
