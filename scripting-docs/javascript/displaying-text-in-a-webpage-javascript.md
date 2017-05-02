---
title: "웹 페이지에서 텍스트 표시(JavaScript) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "JavaScript, 쓰기"
  - "JavaScript, 텍스트 쓰기"
ms.assetid: 3c2455e7-2402-45f2-9545-77a2b2490527
caps.latest.revision: 30
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 27
---
# 웹 페이지에서 텍스트 표시(JavaScript)
웹 페이지에 텍스트를 표시하는 방법은 많습니다.  각 방법은 장단점이 있으며 특정 사용을 지원합니다.  
  
## 텍스트 표시  
  
-   텍스트를 표시하는 권장 방법은 요소를 만들고 해당 [textContent](http://msdn.microsoft.com/ko-kr/e530667f-f8fa-4b6d-a47c-4d5c75e71265) 속성에 쓰는 것입니다.  
  
    ```javascript  
    <div id="textDiv"></div>  
    <script type="text/javascript">  
        var div = document.getElementById("textDiv");  
        div.textContent = "my text";  
        var text = div.textContent;  
    </script>  
    ```  
  
     이 예제에서 `text`의 값은 "my text"입니다.  그러나 부모 노드의 [textContent](http://msdn.microsoft.com/ko-kr/e530667f-f8fa-4b6d-a47c-4d5c75e71265) 속성을 가져오거나 설정하여 생성된 결과 값에는 노드 자식의 텍스트 콘텐츠가 포함될 수 있습니다.  다음 예제에서는 자식 노드에 설정된 [textContent](http://msdn.microsoft.com/ko-kr/e530667f-f8fa-4b6d-a47c-4d5c75e71265)가 부모 노드의 [textContent](http://msdn.microsoft.com/ko-kr/e530667f-f8fa-4b6d-a47c-4d5c75e71265) 값에 포함되는 것을 보여 줍니다.  
  
    ```javascript  
    <div id="textDiv">  
        <div id="nested"></div>  
    </div>  
    <script type="text/javascript">  
        var div = document.getElementById("textDiv");  
        var nestedDiv = document.getElementById("nested");  
        nestedDiv.textContent = "nested";  
  
        var text = "[" + div.textContent + "]";  
    </script>  
    ```  
  
     이 예제에서 `text`의 값은 "\[nested\]"입니다.  
  
-   요소를 만들고 해당 [innerHTML](http://msdn.microsoft.com/library/ie/ms533897\(v=vs.85\).aspx) 또는 [innerText](http://msdn.microsoft.com/library/ie/ms533899\(v=vs.85\).aspx) 속성에 기록을 할 수도 있습니다.  이러한 속성을 설정하면 요소의 자식에 있는 텍스트가 아니라 요소 자체에 있는 텍스트만 영향을 줍니다.  그러나 이러한 속성에는 몇 가지 단점도 있습니다.  
  
    -   [innerText](http://msdn.microsoft.com/library/ie/ms533899\(v=vs.85\).aspx) 속성은 일부 브라우저에서 작동하지 않으므로 호환성을 위해 이 속성을 사용하지 않을 수도 있습니다.  
  
    -   [innerText](http://msdn.microsoft.com/library/ie/ms533899\(v=vs.85\).aspx) 속성은 CSS 스타일의 영향을 받으며 요소가 숨겨진 경우 나타나지 않습니다.  
  
    -   [innerHTML](http://msdn.microsoft.com/library/ie/ms533897\(v=vs.85\).aspx) 속성은 중첩된 노드와 텍스트를 가져오고 설정합니다.  이 속성에 보안을 설정하지 않으면 스크립트 삽입 공격에 사용될 수도 있습니다.  또한 이 속성을 HTML 태그가 없는 텍스트로 설정하면 이전에 설정된 노드가 모두 제거됩니다.  
  
-   요소를 만들 필요 없이 `document.write` 메서드를 사용할 수 있습니다.  그러나 이 메서드를 사용하면 전체 웹 페이지가 지워지므로 주의해야 합니다.  
  
     다음 예제에서는 `document.write`를 사용하는 경우의 단점 중 하나를 보여 줍니다.  스크립트는 5초마다 시간을 표시하도록 작성되었지만 시간을 두 번만 표시합니다.  `document.write`가 두 번째로 호출되는 시점에 페이지 로드가 완료된 다음 `document.write`가 전체 페이지를 지웁니다\(`document.open`을 호출함\).  이 시점에서 `ShowTime` 함수는 더 이상 존재하지 않습니다.  
  
    ```html  
    <!DOCTYPE html>  
    <html>  
    <head>  
    <script type="text/javascript">  
        function ShowTime()  
        {  
            var dt = new Date();  
            document.write(dt.toTimeString());  
            // var elem = document.getElementById("divElem");  
            // elem.textContent = dt.toTimeString();  
            window.setTimeout("ShowTime();", 5000);  
        }  
    </script>  
    </head>  
  
    <body>  
    <script type="text/javascript">  
        ShowTime();  
    </script>  
    <div id="myDiv"></div>  
    </body>  
    </html>  
  
    ```  
  
     위의 코드를 수정하려면 `document.write`를 포함하는 코드 줄을 제거하고 뒤에 나오는 코드에서 주석 처리된 두 줄의 주석 처리를 제거하세요.  
  
-   팝업 창에 메시지를 표시하는 `alert` `prompt` 또는 `confirm` 함수를 사용할 수도 있습니다.  대부분의 경우 웹 브라우저에서 팝업 창을 사용하는 것은 좋지 않습니다.  현재 사용되는 대부분의 브라우저에는 팝업 창을 자동으로 차단하는 설정이 있으므로 메시지가 표시되지 않을 수도 있습니다.  또한 팝업 창을 사용할 때 무한 루프에 들어가 사용자가 일반적인 방법으로 웹 페이지를 닫을 수 없게 될 수도 있습니다.