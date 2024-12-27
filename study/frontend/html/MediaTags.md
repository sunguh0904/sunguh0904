## HTML 미디어 태그
> ### 미디어 관련 태그란?
미디어 관련 태그는 HTML에서 오디오, 비디오 등의 미디어 콘텐츠를 삽입하고 관리하는 데 사용되는 태그</br>
주로 오디오 파일, 비디오 파일을 웹 페이지에 포함하고, 미디어의 속성을 정의하는 데 사용됨

> ### 주요 미디어 관련 태그
1. `<audio>`: 오디오 파일을 삽입하는 태그
    ```html
    <!-- 오디오 파일을 삽입 -->
    <audio controls>
        <source src="audio.mp3" type="audio/mpeg">
        Your browser does not support the audio element.
    </audio>
    ```

2. `<video>`: 비디오 파일을 삽입하는 태그
    ```html
    <!-- 비디오 파일을 삽입 -->
    <video controls>
        <source src="video.mp4" type="video/mp4">
        Your browser does not support the video element.
    </video>
    ```

3. `<source>`: 오디오나 비디오 파일의 소스를 정의하는 태그
    ```html
    <!-- 오디오 파일의 소스를 정의 -->
    <audio controls>
        <source src="audio.mp3" type="audio/mpeg">
        Your browser does not support the audio element.
    </audio>
    <!-- 비디오 파일의 소스를 정의 -->
    <video controls>
        <source src="video.mp4" type="video/mp4">
        Your browser does not support the video element.
    </video>
    ```

4. `<track>`: 비디오 파일의 자막을 정의하는 태그
    ```html
    <!-- 비디오 파일의 자막을 정의 -->
    <video controls>
        <source src="video.mp4" type="video/mp4">
        <track src="subtitles_en.vtt" kind="subtitles" srclang="en" label="English">
        Your browser does not support the video element.
    </video>
    ```

> ### 왜 사용해야 하는가?
1. **미디어 삽입**: 미디어 관련 태그를 사용하면 웹 페이지에 오디오와 비디오를 삽입할 수 있음
2. **미디어 관리**: 미디어의 속성을 정의하고, 자막을 추가하여 미디어를 관리할 수 있음
3. **웹 표준 준수**: HTML 태그를 사용하여 웹 표준을 준수할 수 있음

> ### 쉬운 요약
1. 미디어 관련 태그는 "HTML에서 오디오, 비디오 등의 미디어 콘텐츠를 삽입하고 관리하는 데 사용되는 태그"
    - 주로 오디오 파일, 비디오 파일을 웹 페이지에 포함하고, 미디어의 속성을 정의하는 데 사용됨

2. 미디어 삽입, 미디어 관리, 웹 표준 준수 등을 제공

> ### 비유
1. 영화관
    - 미디어 관련 태그는 영화관과 같음
    - 예: 영화 파일을 삽입하고, 자막을 추가

2. 음악 플레이어
    - 미디어 관련 태그는 음악 플레이어와 같음
    - 예: 음악 파일을 삽입하고, 재생

[뒤로](html.md)
