---
title: "JavaScript에서 Windows 런타임 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "02/03/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "javascript"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "JavaScript, Windows 런타임"
ms.assetid: 90658546-f746-4e34-a7d1-71cf9ee322a2
caps.latest.revision: 16
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 13
---
# JavaScript에서 Windows 런타임 사용
JavaScript를 사용하여 [!INCLUDE[win8_appname_long](../javascript/advanced/includes/win8-appname-long-md.md)] 또는 Windows Phone 스토어 앱을 작성할 때 네이티브 JavaScript 개체, 메서드 및 속성을 사용하는 것과 거의 동일한 방법으로 Windows 런타임 클래스, 메서드 및 속성을 사용할 수 있습니다.  이 항목에서는 Windows 런타임 형식이 표현되는 방법, 비동기 Windows 런타임 메서드를 사용하는 방법 및 Windows 런타임 이벤트를 수신 대기 및 처리하는 방법에 대한 설명을 비롯하여 JavaScript에서 Windows 런타임 API를 사용하는 방법의 기본 개념을 설명하는 기본적인 정보와 이러한 설명 항목의 링크를 제공합니다.  
  
 [JavaScript 언어 참조](../javascript/javascript-language-reference.md)에서 JavaScript 참조 문서를 찾을 수 있습니다.  
  
> [!IMPORTANT]
>  Windows 런타임 기능은 Internet Explorer에서 실행되는 앱에는 사용할 수 없습니다.  
  
## Windows 런타임 참조 문서  
 참조 문서는 [Windows Runtime reference](http://msdn.microsoft.com/ko-kr/8fe97dbf-8cd4-435f-b481-9e83d0519f9e)를 참조하세요.  코드 예제는 JavaScript뿐만 아니라 C\+\+, C\# 및 Visual Basic으로도 제공됩니다.  
  
## C\+\+, C\# 또는 Visual Basic으로 Windows 런타임 구성 요소 작성  
 JavaScript에서 사용할 수 있는 Windows 런타임 구성 요소 작성에 대한 지침과 가이드라인은 [Windows Runtime 구성 요소 만들기](http://msdn.microsoft.com/library/9a6b8f0a-7d5e-40a0-a9c5-a59b4908e133)를 참조하세요.  
  
## Windows 런타임 기능의 대\/소문자 사용 규칙  
 JavaScript에서 Windows 런타임 기능의 대\/소문자 사용 규칙은 다른 언어의 대\/소문자 사용 규칙과 약간 다릅니다.  
  
-   네임스페이스 및 클래스는 파스칼식 대\/소문자로 되어 있습니다.  
  
    ```javascript  
    Windows.Deployment.PackageInfo;  
    ```  
  
-   클래스의 멤버\(메서드 및 속성 포함\)와 구조 및 열거형의 멤버는 카멜식 대\/소문자로 되어 있습니다.  
  
    ```javascript  
    Deployment.PackageInfo.createPackage();  
    ```  
  
-   이벤트 이름으로 소문자로 되어 있습니다.  
  
    ```javascript  
    dataTransferManager.ontargetapplicationchosen;  
    ```  
  
## 참고 항목  
 [Windows 런타임 API를 사용할 때의 고려 사항](../jswinrt/considerations-when-using-the-windows-runtime-api.md)   
 [Windows 런타임 비동기 메서드 사용](../jswinrt/using-windows-runtime-asynchronous-methods.md)   
 [JavaScript에서 Windows 런타임 이벤트 처리](../jswinrt/handling-windows-runtime-events-in-javascript.md)   
 [Windows 런타임 형식의 JavaScript 표현](../jswinrt/javascript-representation-of-windows-runtime-types.md)   
 [Windows 런타임 DateTime 및 TimeSpan의 JavaScript 프로젝션](../jswinrt/windows-runtime-datetime-and-timespan-representations.md)