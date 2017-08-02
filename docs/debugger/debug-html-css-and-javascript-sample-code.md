---
title: "HTML, CSS 및 JavaScript 샘플 코드 디버깅 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: 51893967-98c8-4141-ba40-03646f221760
caps.latest.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 13
---
# HTML, CSS 및 JavaScript 샘플 코드 디버깅
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

![Windows 및 Windows Phone에 적용](~/docs/debugger/media/windows_and_phone_content.png "windows\_and\_phone\_content")  
  
 이 항목의 코드는 다음 항목에 대한 샘플 파일입니다. [퀵 스타트: HTML 및 CSS 디버그](../debugger/quickstart-debug-html-and-css.md).  QuickStart에서 의도적으로 제공되는 오류는 이 버전의 코드에서 수정됩니다.  
  
## 샘플 코드  
 다음 HTML 코드는 QuickStart의 \<body\> 태그에서 사용됩니다.  
  
```html  
<div id="flipTemplate" data-win-control="WinJS.Binding.Template"  
         style="display:none">  
    <div class="fixedItem" >  
        <img src="#" data-win-bind="src: flipImg" />  
    </div>  
</div>  
<div id="fView" data-win-control="WinJS.UI.FlipView" data-win-options="{  
    itemDataSource: Data.items.dataSource, itemTemplate: flipTemplate }">  
</div>  
```  
  
 다음 CSS에서는 default.css에 추가된 내용을 보여 줍니다.  
  
```css  
#fView {  
    background-color:#0094ff;  
    height: 500px;  
    margin: 25px;  
}  
```  
  
 다음 코드 예제에서는 default.js의 전체 JavaScript 코드를 보여 줍니다.  이 코드의 WinJS 네임스페이스에 대한 참조는 템플릿의 default.html 파일에 있습니다.  
  
```javascript  
(function () {  
    "use strict";  
  
    var app = WinJS.Application;  
    var activation = Windows.ApplicationModel.Activation;  
  
    var myData = [];  
    for (var x = 0; x < 4; x++) {  
        myData[x] = { flipImg: "/images/logo.png" }  
    };  
  
    var pages = new WinJS.Binding.List(myData, { proxy: true });  
  
    app.onactivated = function (args) {  
        if (args.detail.kind === activation.ActivationKind.launch) {  
            if (args.detail.previousExecutionState !==  
            activation.ApplicationExecutionState.terminated) {  
                // TODO: . . .  
            } else {  
                // TODO: . . .  
            }  
            args.setPromise(WinJS.UI.processAll());  
  
            updateImages();  
        }  
    };  
  
    function updateImages() {  
  
        pages.setAt(0, { flipImg: "http://go.microsoft.com/fwlink/?LinkID=223195" });  
        pages.setAt(1, { flipImg: "http://go.microsoft.com/fwlink/?LinkID=223196" });  
        pages.setAt(2, { flipImg: "http://go.microsoft.com/fwlink/?LinkID=223197" });  
    };  
  
    app.oncheckpoint = function (args) {  
    };  
  
    app.start();  
  
    var publicMembers = {  
        items: pages  
    };  
  
    WinJS.Namespace.define("Data", publicMembers);  
  
})();  
```  
  
## 참고 항목  
 [퀵 스타트: HTML 및 CSS 디버그](../debugger/quickstart-debug-html-and-css.md)