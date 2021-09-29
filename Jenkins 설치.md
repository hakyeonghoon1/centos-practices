# Jenkins

## Jenkins 2.313설치

1. **wget을 통한 Jenkins 설치 (/root에서)**
    
    ```
    wget [https://get.jenkins.io/war-stable/2.303.1/jenkins.war](https://get.jenkins.io/war-stable/2.303.1/jenkins.war)
    ```
    
                                                                         (Jenkins 홈페이지 [https://www.jenkins.io/download/](https://www.jenkins.io/download/))
    

1. **jenkins.war을 tomcat/webapps로 이동**
    
    ```
    mv jenkins.war /usr/local/douzone/tomcat/webapps/
    ```
    

1. **jenkins 기본 실행 화면**
    
    ```
    url : 127.0.0.1/jenkins 검색
    ```
    
    ![Untitled](Jenkins%20a95c04dd0d96428cae7c931b4352b403/Untitled.png)
    

1. **Jenkins Unlock & 추천 플로그인 설치**
    
    ![Untitled](Jenkins%20a95c04dd0d96428cae7c931b4352b403/Untitled%201.png)
    
    - 해당 디렉토리에서 initialAdminPassword에 숨겨져있다. cat을 통해 암호 확인 가능 → jenkins 기본 실행 화면에 암호 입력 → install 선택
    
    ![Untitled](Jenkins%20a95c04dd0d96428cae7c931b4352b403/Untitled%202.png)
    
    ![Untitled](Jenkins%20a95c04dd0d96428cae7c931b4352b403/Untitled%203.png)
    
2. **회원 가입**
    
    ![Untitled](Jenkins%20a95c04dd0d96428cae7c931b4352b403/Untitled%204.png)
    
3. **Jenkins JDK & git & maven 설정**
    
    ![Untitled](Jenkins%20a95c04dd0d96428cae7c931b4352b403/Untitled%205.png)
    
    ![Untitled](Jenkins%20a95c04dd0d96428cae7c931b4352b403/Untitled%206.png)
    
    ![Untitled](Jenkins%20a95c04dd0d96428cae7c931b4352b403/Untitled%207.png)
    

1. **새 프로젝트 생성**
    
    ![Untitled](Jenkins%20a95c04dd0d96428cae7c931b4352b403/Untitled%208.png)
    

1. 새 프로젝트 셋팅
    - 해당 github repository URL을 입력해준다.
        
        ![Untitled](Jenkins%20a95c04dd0d96428cae7c931b4352b403/Untitled%209.png)
        
    - build
        
        ![Untitled](Jenkins%20a95c04dd0d96428cae7c931b4352b403/Untitled%2010.png)
        
    
    1. **build 하기**
    
    ![Untitled](Jenkins%20a95c04dd0d96428cae7c931b4352b403/Untitled%2011.png)
    
    - Build Now를 통해 build를 할 수 있으며,  왼쪽 아래에서 실행 결과를 확인할 수 있다.
    - Jenkins에서 빌드 기록과 현재 상태 등을 알 수 있따.