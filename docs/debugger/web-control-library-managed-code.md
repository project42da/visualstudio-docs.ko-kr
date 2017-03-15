---
title: "웹 컨트롤 라이브러리(관리 코드) | Microsoft Docs"
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
helpviewer_keywords: 
  - "디버깅[Visual Studio], 웹 컨트롤 라이브러리"
  - "DLL 디버깅"
ms.assetid: 2413883f-9e88-406d-b874-0ed743b75d40
caps.latest.revision: 26
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 26
---
# 웹 컨트롤 라이브러리(관리 코드)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

웹 컨트롤 라이브러리 프로젝트 템플릿은 DLL을 만듭니다.  클래스 라이브러리는 DLL이므로 직접 실행할 수 없고,  컨트롤을 포함하는 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 페이지를 만들어야 합니다.  자세한 내용은 [Web Control Library Template](http://msdn.microsoft.com/ko-kr/00666b07-71d2-4ace-a13c-cc130a3ce372)을 참조하십시오.  
  
### 웹 컨트롤 라이브러리를 디버깅하려면\(방법 1\)  
  
1.  기존의 웹 컨트롤 라이브러리 프로젝트를 열거나 새 프로젝트를 만듭니다.  
  
2.  컨트롤을 포함하는 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 페이지를 만듭니다.  
  
3.  [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 테스트 환경을 호스팅하는 웹 사이트에 `/Code`라는 하위 디렉터리를 만듭니다.  
  
4.  컨트롤의 소스 코드를 `/Code` 하위 디렉터리에 복사합니다.  
  
5.  `/Code` 하위 디렉터리에서 소스 코드를 열고 중단점을 설정합니다.  
  
6.  브라우저 창을 열고 테스트 환경을 가리키는 URL을 입력합니다.  컨트롤에서 중단점에 도달하면 디버깅을 시작할 수 있습니다.  
  
### 웹 컨트롤 라이브러리를 디버깅하려면\(방법 2\)  
  
1.  호스트 응용 프로그램 프로젝트와 웹 컨트롤 프로젝트를 동일한 솔루션에 만듭니다.  
  
2.  **솔루션 탐색기**에서 호스트 응용 프로그램을 마우스 오른쪽 단추로 클릭하고 **참조 추가**를 선택합니다.  
  
3.  웹 컨트롤 프로젝트에 참조를 추가합니다.  
  
## 참고 항목  
 [ASP.NET 웹 응용 프로그램](../debugger/debugging-preparation-aspnet-web-applications.md)