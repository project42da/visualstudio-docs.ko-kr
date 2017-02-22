---
title: "방법: 프로그램에서 충돌이 발생하는 DLL 찾기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.debug.dll"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "디버거, DLL 충돌"
  - "디버깅[Visual Studio], DLL 충돌"
  - "DLL, 로드 순서"
  - "오류[디버거], DLL 충돌"
  - "모듈 목록 대화 상자"
  - "모듈 창"
ms.assetid: ecf62568-8b65-4a41-b8a4-e962ff2dfb71
caps.latest.revision: 17
caps.handback.revision: 17
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 방법: 프로그램에서 충돌이 발생하는 DLL 찾기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 도구 메뉴에서 설정 가져오기 및 내보내기를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
 시스템 DLL 또는 다른 사람의 코드를 호출하는 동안 응용 프로그램에 충돌이 발생하면 충돌 발생 시 활성 상태였던 DLL을 찾아야 합니다.  사용자 프로그램 외부에서 DLL에 충돌이 발생하는 경우 **모듈** 창을 사용하여 위치를 확인할 수 있습니다.  
  
### 모듈 창을 사용하여 충돌이 발생한 위치를 찾으려면  
  
1.  충돌이 발생한 주소를 기록합니다.  
  
2.  **디버그** 메뉴에서 **창**을 선택한 다음 **모듈**을 클릭합니다.  
  
3.  **모듈** 창에서 **주소** 열을 찾습니다.  이 열을 표시하려면 스크롤 막대를 사용해야 할 수도 있습니다.  
  
4.  주소별로 DLL을 정렬하려면 열 맨 위에 있는 **주소** 단추를 클릭합니다.  
  
5.  정렬된 목록을 조사하여 충돌 위치가 속하는 주소 범위를 가진 DLL을 찾습니다.  
  
6.  **이름** 및 **경로** 열에서 DLL 이름과 경로를 확인합니다.  
  
## 참고 항목  
 [방법: 네이티브 DLL 디버깅](../debugger/how-to-debug-native-dlls.md)   
 [방법: 모듈 창 사용](../debugger/how-to-use-the-modules-window.md)