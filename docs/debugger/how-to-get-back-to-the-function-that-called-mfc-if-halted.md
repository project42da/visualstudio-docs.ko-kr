---
title: "방법: 중지된 경우 MFC를 호출한 함수로 돌아가기 | Microsoft Docs"
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
  - "vs.debug.mfc"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
  - "C++"
helpviewer_keywords: 
  - "중단 명령"
  - "디버깅[MFC], 함수"
  - "디버깅[MFC], 호출 함수로 반환"
  - "함수 호출, 호출 함수로 반환"
  - "함수[C++], 디버깅"
  - "함수[디버거]"
  - "프로그램, 중지"
ms.assetid: d254a5a9-afbd-4923-9d7a-7422d824cabf
caps.latest.revision: 18
caps.handback.revision: 18
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 방법: 중지된 경우 MFC를 호출한 함수로 돌아가기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 도구 메뉴에서 설정 가져오기 및 내보내기를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
 **디버그** 메뉴의 **중단** 명령을 사용하여 프로그램을 중단했을 때 MFC에서 중지되었고 코드에 문제가 있다고 판단되면 호출 스택 창을 사용하여 함수로 되돌아갈 수 있습니다.  자세한 내용은 [방법: 호출 스택 창 사용](../debugger/how-to-use-the-call-stack-window.md)을 참조하십시오.  
  
 때로는 코드가 메시지 펌프에서 손상될 수도 있습니다.  그럴 경우 호출 스택에는 사용자 코드가 들어 있지 않습니다.  이 문제가 발생하지 않도록 하려면 **중단** 명령 대신 중단점을 사용합니다. 이 경우 조건 및 적중 횟수도 함께 사용할 수 있습니다.  자세한 내용은 [Breakpoints and Tracepoints](http://msdn.microsoft.com/ko-kr/fe4eedc1-71aa-4928-962f-0912c334d583)을 참조하십시오.  
  
### MFC를 호출한 함수를 탐색하려면  
  
-   **호출 스택** 창을 사용합니다.  
  
## 참고 항목  
 [네이티브 코드 디버깅 FAQ](../debugger/debugging-native-code-faqs.md)   
 [네이티브 코드 디버깅](../debugger/debugging-native-code.md)