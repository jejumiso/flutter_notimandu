https://www.youtube.com/watch?v=u-7ut-phOrA

소스 따라 하는건 위에 유튜브 자료.
구글등 여러개 따라 했으나 전부 실패 ㅠㅠ


1. GoogleService-info.plist 파일하고
2. 구글콘솔에 파일 추가 

* 1~2 : flutterfire로 자동 추가함... 
        수동 추가한것과 차이는 없을것 같음...

         에뮬에서는 token이 정상적으로 나옴
         디바이스에서는 에러 뜸...
            An error occurred while calling method Messaging#getToken, errorOrNil
            No APNS token specified before fetching FCM Token

         에뮬에서는 APNSToken토큰(?)이 없어도 되지만 디바이스에서는 APNSToken을 필요로 하는것 같다.

        문제를 해결 하기 위해서 구글콘솔에 인증서를 올려주는등 해봤지만 안됨.. 올렸던 인증서 지우고 다시 한번 진행 예정.


3. 애플개발자에서 키생성
    서비스 : 애플푸시노티피케이션 (생성할때 체크한거)
    이름 : pushnotification (임의로 이름 지은것)
   
4. xcode에서 background 하고 push notification 추가
   => 애플개발자에 자동으로 추가됨.

5. 구글 콘솔-> 설정 -> 클라우드메시징 에서
   4의 인증키 등록

 * APN인증키 등록 3~5 : 역시나 에뮬에서만 되고 디바이스에서는 안됨..
 * APN인증서 등록은 안했음 : 하는게 어렵진 않지만 나중에 해볼 예정. 둘중하나만 등록 하면 되는것 같으니.. 혹 모르니 나중에 둘다 해보자..


6. Runner > AppDelegate.swift 파일 수정 (유튜브 내용 참조)


7. APN인증서 등록 : 등록해도 안되네..