# File upload

- Spring boot를 이용하여 S3에 이미지 파일을 업로드 할때 그렇게 크지않은용량도 에러가 떠서 찾아본 내용 [ S3로 업로드 직전에 에러가 터짐 ] 

```
multipart.MaxUploadSizeExceededException: 
Maximum upload size exceeded; nested exception is java.lang.IllegalStateException: 
org.apache.tomcat.util.http.fileupload.FileUploadBase$FileSizeLimitExceededException: 
The field sourceFile exceeds its maximum permitted size of 1048576 bytes.
```

- 스프링부트의 디폴트 최대값은 1048576 bytes로 약 1MB로 이를넘을시 undefined로 데이터가나옴
- 해당내용의 해결은 application.properties에서 설정 변경


```
스프링 버전에따라 선언이 다를수있음.

spring.servlet.multipart.max-file-size=10MB
spring.servlet.multipart.max-request-size=10MB
```

