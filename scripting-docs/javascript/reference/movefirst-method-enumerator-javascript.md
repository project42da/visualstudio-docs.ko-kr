---
title: "moveFirst 메서드(Enumerator)(JavaScript) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "moveFirst"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "MoveFirst 메서드"
ms.assetid: 96eedc66-7974-443c-b0cd-55373a7c0e59
caps.latest.revision: 18
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 18
---
# moveFirst 메서드(Enumerator)(JavaScript)
컬렉션의 현재 항목을 첫 번째 항목으로 다시 설정합니다.  
  
> [!WARNING]
>  이 개체는 Internet Explorer에서만 지원됩니다.  
  
## 구문  
  
```  
  
enumObj.moveFirst( )  
```  
  
## 설명  
 필요한 *enumObj* 참조는 모든 `Enumerator` 개체입니다.  
  
 컬렉션에 항목이 없는 경우 현재 항목이 undefined로 설정됩니다.  
  
## 예제  
 다음 예제에서는 목록의 시작 부분에서 `Drives` 컬렉션의 멤버를 평가하기 위해 `moveFirst` 메서드가 사용됩니다.  
  
```javascript  
function ShowDrives()  
{  
    var s = "";  
    var bytesPerGB = 1024 * 1024 * 1024;  
  
    var fso = new ActiveXObject("Scripting.FileSystemObject");  
    var e = new Enumerator(fso.Drives);  
  
    e.moveFirst();  
    while (e.atEnd() == false)  
    {  
        var drv = e.item();  
  
        s += drv.Path + " - ";  
  
        if (drv.IsReady)  
        {  
            var freeGB = drv.FreeSpace / bytesPerGB;  
            var totalGB = drv.TotalSize / bytesPerGB;  
  
            s += freeGB.toFixed(3) + " GB free of ";  
            s += totalGB.toFixed(3) + " GB";  
        }  
        else  
        {  
            s += "Not Ready";  
        }  
  
        s += "<br />";  
  
        e.moveNext();  
    }  
    return(s);  
}  
```  
  
## 요구 사항  
 지원되는 문서 모드: Quirks, Internet Explorer 6 표준, Internet Explorer 7 표준, Internet Explorer 8 표준, Internet Explorer 9 표준 및 Internet Explorer 10 표준[!INCLUDE[win8_appname_long](../../javascript/advanced/includes/win8-appname-long-md.md)] 앱에서는 지원되지 않습니다.[버전 정보](../../javascript/reference/javascript-version-information.md)를 참조하십시오.  
  
 **적용 대상**: [Enumerator 개체](../../javascript/reference/enumerator-object-javascript.md)  
  
## 참고 항목  
 [atEnd 메서드\(Enumerator\)](../../javascript/reference/atend-method-enumerator-javascript.md)   
 [item 메서드\(Enumerator\)](../../javascript/reference/item-method-enumerator-javascript.md)   
 [moveNext 메서드\(Enumerator\)](../../javascript/reference/movenext-method-enumerator-javascript.md)