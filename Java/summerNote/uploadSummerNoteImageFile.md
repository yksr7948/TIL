# SummerNote 이미지 파일 업로드 하기

오늘은 프로젝트에 텍스트 에디터를 추가하는 방법에 대해 공부했다.
SummerNote는 JQury와 BootStrap 기반으로 만들어진 오픈소스 프로젝트이다.

<br><br>

## 구현 순서
1. CDN 적용 & 자바스크립트 구현
2. AJAX 구현
3. Controller 구현
4. Configuration 구현

<br><br>
### 1. CDN 적용 & 자바스크립트 구현

![image](https://github.com/user-attachments/assets/ebe1ae72-8ccc-452c-8928-b6bdc2f14e59)

![image](https://github.com/user-attachments/assets/bcedcc73-bc7c-40bf-b042-becff26123aa)

서머노트 공식 문서에 들어가면 간단하게 이렇게 작성하면 서머노트 에디터를 불러올 수 있다.

Summernote는 다양한 커스터마이즈를 지원한다.  메뉴바의 구성 각 구성요소에 상세 요소까지 설정이 가능하다. 

![image](https://github.com/user-attachments/assets/afa6b74d-23d9-4e06-88a4-6b8537e0bf50)

이런식으로 툴바를 꾸며주었고, setting 객체 리터럴 안에 callbacks라는 요소를 추가하였다.

callback에서 사용되는 함수는 이미지 업로드 시에 사용하는 함수인데 원래는 그냥 사용해도 이미지 업로드가 잘 된다.

![image](https://github.com/user-attachments/assets/535defbf-67bf-416e-8ce7-cb8144536ffa)

img파일이 base64 코드로 인코딩 되어서 넘어오는 것을 확인할 수 있었고 이 코드를 데이터베이스에 저장하기에는 무리일 거 같아서 따로 이미지업로드 하는 방법을 만들었다.

<hr>
<br><br>

### 2. AJAX 구현

자바스크립트에서 이미지 업로드 시 만들었던 함수를 ajax를 이용해서 img를 전달해 주었다.

![image](https://github.com/user-attachments/assets/54ec5e43-1998-40bb-8ee8-a91073739726)

전달하는 데이터가 이미지 파일이므로 data = new Data()로 객체를 생성해주었다. FormData는 html 폼 데이터를 생성하고, 이 객체를 사용해야지 서버로 데이터를 보낼수 있다.

contentType: false로 설정하면 jQury가 자동으로 적절한 contentType을 설정해 준다.

processData: false로 설정하면 jQury가 데이터를 쿼리 스트링 형태로 처리하지 않고 그대로 전송한다.

$(editor).summernote('insertImage', contextPath + data.url); : 이 메서드를 사용하여 이미지 URL을 서머노트 에디터에 삽입할 수 있음.

<hr>
<br><br>

### 3. Controller 구현

![image](https://github.com/user-attachments/assets/51d8ea38-031b-406d-a9e1-378ec327fda8)

Ajax로 전달한 데이터를 controller에서 받아주었다. 여기서는 이미지 파일이 저장될 경로랑 서버에 저장되는 이름을 바꿔주는 작업을 해주었는데 나중에 배포할때 외부파일에다가 저장하는 방법을 사용한다고 했다. (재배포시 이미지파일 다 날라감)

하지만 아직은 배포 전이라 관리하기 쉬운 프로젝트 안에 경로를 잡아주었다.

<hr>
<br><br>

### 4. Configuration 구현

![image](https://github.com/user-attachments/assets/95bdc889-e09f-4656-a222-acf2e78ee089)

마지막으로 Configuration 설정을 통해 이미지 업로드가 정상적으로 됐다.

/summernoteImage/로 시작하는 URL요청이 들어올 때, 파일 시스템에서 upoloadPath 경로에 있는 파일을 제공할 수 있도록 리소스 핸들러를 등록해 주었다. 

여기에서 404에러가 많이 났는데 AJax에서 data.url에 앞에 contextPath를 빼먹어서 404에러가 났었다.




