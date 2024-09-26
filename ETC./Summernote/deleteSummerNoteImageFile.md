# 페이지 벗어날 때 이미지 파일 삭제하기

오늘은 서머노트에서 이미지를 업로드 하고 저장하지 않고 페이지 나갔을 때 서버에 올라간 이미지 파일은 삭제하는 작업을 했다.


## JS코드

![image](https://github.com/user-attachments/assets/127f6f8f-f014-47a4-8c98-54af135e64dd)

먼저 이미지 파일들을 담아 놓을 빈 문자열 변수와, 폼 제출인지 판별해주는 변수를 만들어 주었다.

![image](https://github.com/user-attachments/assets/1f807267-4df5-4bf6-a8dd-bb92c87b9baa)

이미지가 업로드 되었을 때, 서머노트 에디터 안에 이미지 파일을 넣어주었고, imgs변수 안에 담아주었다.

![image](https://github.com/user-attachments/assets/a69d5dae-106a-4fe0-9e00-3add55a8008d)

여기서는 JavaScript의 beforeunload이벤트를 사용했다.

[Window: beforeunload 이벤트 공식 문서](https://developer.mozilla.org/ko/docs/Web/API/Window/beforeunload_event)

해당 이벤트는 사용자가 새로고침, 뒤로가기, 브라우저 닫기, 폼 제출 등의 액션을 취하면 발동된다.

내가 원하는 것은 폼 제출 시만 빼고 해당 이벤트를 걸고 싶으니 위에서 만들어 주었던 isFormSubmitting이 submit 상태일 때만 true값으로 바꿔주었다.

<hr>
<br><br>

## Controller

![image](https://github.com/user-attachments/assets/ae82af3f-dd52-4f04-85d5-554268ff456b)

Controller에서는 이미지 업로드 시에 담아놨던 imgs 변수를 받아주었고 여기에서 split메소드를 이용해 이미지 파일 이름들을 문자열 배열인 fileNames에 담아주었다.

fileNames를 for문을 돌려 해당 이름을 가진 파일이 존재하는 경우 서버에서 삭제 요청을 했다.




