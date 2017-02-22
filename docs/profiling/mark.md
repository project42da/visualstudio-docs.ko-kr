---
title: "표시 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1d72cef3-bb09-4bbb-8864-6ea0ab623ff9
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 표시
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

VSPerfCmd.exe의 **Mark** 옵션은 프로파일링 데이터 파일에 지정된 정보를 삽입합니다.  표시는 별도의 VSPerfReport 보고서나 프로파일러 UI의 표시 보고서 뷰에 나열될 수 있습니다.  **Mark**는 보고서 및 보기 필터에 시작 지점과 끝 지점을 지정하는 데 사용할 수 있습니다.  
  
 **Mark** 옵션은 명령줄에서 단독으로 지정해야 합니다.  
  
## 구문  
  
```  
VSPerfCmd.exe /Mark:MarkID,[MarkName]   
```  
  
#### 매개 변수  
 `MarkID`  
 프로파일러 뷰 및 보고서에서 표시 ID로 나열되는 사용자 정의 정수입니다.  `MarkID`는 고유하지 않아도 됩니다.  
  
 `MarkName`  
 선택적 요소로서, 프로파일러 뷰 및 보고서에서 표시 이름으로 나열되는 사용자 정의 문자열입니다.  `MarkName`을 지정하지 않을 경우 표시 목록의 표시 이름 필드는 비어 있습니다.  공백이나 슬래시\("\/"\)가 포함된 문자열은 따옴표로 묶습니다.  
  
## 예제  
 이 예제에서는 ID가 123이고 표시 이름이 "TestMark"인 표시를 삽입합니다.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe  
VSPerfCmd.exe /Mark:123,TestMark  
```  
  
## 참고 항목  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [독립 실행형 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET 웹 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [서비스 프로파일링](../profiling/command-line-profiling-of-services.md)