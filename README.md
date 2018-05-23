# CefGlue_Example

WPF Project에서 Chromium Browser를 사용하기 위한 LIB.

대표적으로 CefSharp을 가장 많이 쓰지만 Wpf 버전에서 한글 입력이 한박자 느린 Issue로 인해 대안으로 찾아 보았으나 마찬가지 이슈가 발생됨.

Winform으로 구현시 두 개의 프로젝트 모두 한글 입력에서 문제는 없으나 Wpf 에서만 발생 된다.

https://github.com/cefsharp/CefSharp/issues/1262
(18년 3월에 글을 올려둔 것으로 보아 여전히 문제는 수정되지 않은 것으로 보임)

CefGlue의 경우 Document 또는 다른 Guide 문서가 없는 것으로 보여 빌드 하는데 애를 먹었다..

Build 조건
- http://opensource.spotify.com/cefbuilds/index.html
  -상기 링크에서 원하는 바이너리 다운로드.
  - Project Version.g.cs에 해당하는 'CEF' 의 바이너리를 실행 시키고자 하는 위치에 포함해줘야 한다.
    - 나의 경우 Version.g.cs의 버전이 Latest CEF의 버전보다 낮았기에 g.cs 파일을 수정했다 (주석에는 고치지 말라고 써있긴 함)
    - 넣지 않을 경우 'libcef.dll'을 로드할 수 없다' 라는 오류 팝업 발생.
  - 또 바이너리를 다운 받은 곳에서 'Resources' 폴더 하위 모든 폴더를 실행 시키고자 하는 위치에 포함해줘야 한다.
    - 넣지 않을 경우 'Invalid file descriptor to ICU data received' 에러 뱉어내고 종료됨.
  - 빌드옵션을 x86으로 설정하고 실행하면 된다.
  - 나의 경우 Debug Mode로 실행 시 WPF 버전의 브라우저가 로딩이 되지 않았다.
