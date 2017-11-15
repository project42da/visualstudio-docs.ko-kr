---
title: "웹 페이지에서 텍스트 표시(JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- JavaScript, write
- JavaScript, writing text
ms.assetid: 3c2455e7-2402-45f2-9545-77a2b2490527
caps.latest.revision: "30"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a8c9ea9d0e0300a0d9b71b0b33d7c99c9ac3935c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="displaying-text-in-a-webpage-javascript"></a>웹 페이지에서 텍스트 표시(JavaScript)
웹 페이지에 텍스트를 표시하는 방법은 여러 가지입니다. 각각 장점과 단점이 있고 특정 용도를 지원합니다.  
  
## <a name="displaying-text"></a>텍스트 표시  
  
-   텍스트를 표시하는 권장 방법은 요소를 만들고 해당 textContent 속성에 쓰는 것입니다.  
  
    ```JavaScript  
    <div id="textDiv"></div>  
    <script type="text/javascript">  
        var div = document.getElementById("textDiv");  
        div.textContent = "my text";  
        var text = div.textContent;  
    </script>  
    ```  
  
     이 예제에서 `text`의 값은 "my text"입니다. 하지만 부모 노드의 `textContent` 속성을 가져오거나 설정하여 얻는 값은 노드의 자식에 있는 텍스트 콘텐츠를 포함할 수도 있습니다. 다음 예제에서는 자식 노드에 대해 설정된 `textContent`가 부모 노드의 `textContent` 값에 포함되어 있음을 보여 줍니다.  
  
    ```JavaScript  
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
  
     이 예제에서 `text`의 값은 "[nested]"입니다.  
  
-   요소를 만들고 [innerHTML](http://msdn.microsoft.com/library/ie/ms533897\(v=vs.85\).aspx) 또는 [innerText](http://msdn.microsoft.com/library/ie/ms533899\(v=vs.85\).aspx) 속성에 기록할 수도 있습니다. 이러한 속성을 설정하면 요소의 자식에 있는 텍스트가 아니라 요소 자체에 있는 텍스트만 영향을 줍니다. 그러나 이러한 속성에는 몇 가지 단점도 있습니다.  
  
    -   [innerText](http://msdn.microsoft.com/library/ie/ms533899\(v=vs.85\).aspx) 속성은 일부 브라우저에서 작동하지 않으므로 호환성을 위해 이 속성을 사용하지 않으려고 할 수도 있습니다.  
  
    -   [innerText](http://msdn.microsoft.com/library/ie/ms533899\(v=vs.85\).aspx) 속성은 CSS 스타일의 영향을 받으며 요소가 숨겨진 경우 나타나지 않습니다.  
  
    -   [innerHTML](http://msdn.microsoft.com/library/ie/ms533897\(v=vs.85\).aspx) 속성은 중첩 노드 및 텍스트를 가져오고 설정합니다. 이 속성에 보안이 설정되지 않으면 스크립트 삽입 공격에 사용될 수도 있습니다. 또한 이 속성을 HTML 태그가 없는 텍스트로 설정하면 이전에 설정된 노드가 모두 제거됩니다.  
  
-   요소를 만들 필요 없이 `document.write` 메서드를 사용할 수 있습니다. 그러나 이 메서드를 사용하면 전체 웹 페이지가 지워지므로 주의해야 합니다.  
  
     다음 예제에서는 `document.write`를 사용하는 경우의 단점 중 하나를 보여 줍니다. 스크립트는 5초마다 시간을 표시하도록 작성되었지만 시간을 두 번만 표시합니다. `document.write`가 두 번째로 호출되는 시점에 페이지 로드가 완료된 다음 `document.write`가 전체 페이지를 지웁니다(`document.open`을 호출함). 이 시점에서 `ShowTime` 함수는 더 이상 존재하지 않습니다.  
  
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
  
-   팝업 창에 메시지를 표시하는 `alert``prompt` 또는 `confirm` 함수를 사용할 수도 있습니다. 대부분의 경우 웹 브라우저에서 팝업 창을 사용하는 것은 좋지 않습니다. 현재 사용되는 대부분의 브라우저에는 팝업 창을 자동으로 차단하는 설정이 있으므로 메시지가 표시되지 않을 수도 있습니다. 또한 팝업 창을 사용할 때 무한 루프에 들어가 사용자가 일반적인 방법으로 웹 페이지를 닫을 수 없게 될 수도 있습니다.