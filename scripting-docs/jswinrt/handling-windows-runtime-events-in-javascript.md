---
title: "JavaScript의 Windows 런타임 이벤트 처리 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: javascript
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JavaScript, Windows Runtime events
- Windows Runtime events [JavaScript]
ms.assetid: d9436aff-2c30-4846-b8df-eaa3e63fd75c
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e963472ee51f2439b50807a49425dcd7f6d8443a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="handling-windows-runtime-events-in-javascript"></a>JavaScript의 Windows 런타임 이벤트 처리
Windows 런타임 이벤트는 C++ 또는 .NET Framework에서 표현되는 방식과 다른 방식으로 JavaScript에서 표현됩니다. Windows 런타임 이벤트는 클래스 속성이 아니며 클래스의 `addEventListener` 및 `removeEventListener` 메서드에 전달되는 문자열 식별자로 표현됩니다. 예를 들어 “positionchanged” 문자열을 `Geolocator.addEventListener` 메서드에 전달하여 [Geolocator.PositionChanged](http://msdn.microsoft.com/library/windows/apps/xaml/windows.devices.geolocation.geolocator.positionchanged.aspx) 이벤트의 이벤트 처리기를 추가할 수 있습니다.  
  
```JavaScript  
var locator =  new Windows.Devices.Geolocation.Geolocator();  
locator.addEventListener(  
    "positionchanged",   
     function (ev) {  
        console.log("Got event");  
    });  
```  
  
 또한 `locator.onpositionchanged` 속성을 설정할 수도 있습니다.  
  
```  
locator.onpositionchanged =    
    function (ev) {  
        console.log("Got event");  
    };  
```  
  
 JavaScript에서 Windows 런타임 이벤트 인수는 단일 이벤트 개체로 표현됩니다. 다음 이벤트 처리기 메서드 예제에서 `ev` 매개 변수는 보낸 사람(대상 속성) 및 기타 이벤트 인수 둘 다를 포함하는 개체입니다. 이벤트 인수는 각 이벤트에 대해 문서화되는 인수입니다.  
  
```JavaScript  
function (ev) {  
    console.log("Target: " + ev.target);  
    console.log("Position: " +  
        ev.position.latitude + "," +  
        ev.position.longitude);  
};  
  
```  
  
> [!IMPORTANT]
>  Windows 런타임 기능은 Internet Explorer에서 실행되는 앱에는 사용할 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [JavaScript에서 Windows 런타임 사용](../jswinrt/using-the-windows-runtime-in-javascript.md)