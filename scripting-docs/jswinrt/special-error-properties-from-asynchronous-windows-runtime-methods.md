---
title: "비동기 Windows 런타임 메서드의 특수한 오류 속성 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "javascript"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 45155584-06d8-4e7f-93a6-8564a93f643d
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 2
---
# 비동기 Windows 런타임 메서드의 특수한 오류 속성
콜 스택의 깊은 곳에서 오류가 throw될 수 있기 때문에 JavaScript에서 비동기 Windows 런타임 메서드를 디버깅하는 것은 어렵습니다.  JavaScript `Error` 개체는 응용 프로그램이 디버깅 모드에서 실행될 때 비동기 Windows 런타임 메서드에서 오류가 throw될 경우에만 나타나는 추가 속성이 있습니다.  
  
## 특수 오류 속성  
 디버그 모드에서 실패한 Windows 런타임 비동기 작업으로 발생한 오류 개체에는 다음과 같은 특수 속성이 있습니다.  
  
-   `asyncOpSource`\(개체\) 오류가 발생한 호출의 원래 위치 정보를 가져옵니다.  `asyncOpSource.originatingCall`\(문자열\) 속성은 사용자 코드에서 비동기 작업이 발생한 위치를 표시합니다.  
  
-   asyncOpType\(문자열\)은 오류가 발생한 비동기 작업 형식의 이름을 가져옵니다.  
  
 비동기 작업이 포함된 오류에 대한 자세한 내용은 다음을 참조하십시오.  
  
-   [How to handle errors with promises](http://msdn.microsoft.com/ko-kr/01d5a901-c4ea-46f6-8005-6d39c32203eb)  
  
-   [Windows 런타임 오류 문제 해결](http://msdn.microsoft.com/ko-kr/1ef7d7df-82ac-441d-8ad0-54ab1318de64)