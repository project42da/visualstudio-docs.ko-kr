---
title: "Windows API 함수를 어떻게 디버깅할 수 있습니까? | Microsoft Docs"
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
  - "vs.debug.api"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
  - "C++"
helpviewer_keywords: 
  - "API, 디버깅"
  - "디버깅[C++], Windows API 함수"
  - "NT 기호 및 Windows API 함수 디버깅"
  - "Windows API 함수, 디버깅"
  - "Windows API, API 함수 디버깅"
ms.assetid: 7c126f57-62ab-4d94-9805-632d696ba1f0
caps.latest.revision: 20
caps.handback.revision: 20
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# Windows API 함수를 어떻게 디버깅할 수 있습니까?
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

NT 기호가 로드된 Windows API 함수를 디버깅하려면 다음 작업을 수행해야 합니다.  
  
### NT 기호가 있는 Windows API 함수에 중단점을 설정하려면  
  
-   함수가 상주하는 DLL 이름과 함수 이름을 함께 입력합니다.  32비트 코드에서는 함수 이름의 데코레이팅된 형식을 사용합니다.  예를 들어 **MessageBeep**에 중단점을 설정하려면 다음을 입력해야 합니다.  
  
    ```  
    {,,USER32.DLL}_MessageBeep@4  
    ```  
  
     데코레이팅된 이름을 확인하려면 [Viewing Decorated Names](http://msdn.microsoft.com/ko-kr/f79e2717-a4db-4d12-a689-69830cce2be0)를 참조하십시오.  
  
## 참고 항목  
 [네이티브 코드 디버깅 FAQ](../debugger/debugging-native-code-faqs.md)   
 [네이티브 코드 디버깅](../debugger/debugging-native-code.md)