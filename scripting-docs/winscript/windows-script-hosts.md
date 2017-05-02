---
title: "Windows 스크립트 호스트 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Windows 스크립트 호스트, 호스트 구현"
ms.assetid: 9d5f6471-b318-40f3-be01-d9cd0b1cdd47
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# Windows 스크립트 호스트
Microsoft Windows 스크립트 호스트를 구현 하는 경우 스크립팅 엔진에만 호출 하는 가정할 수 있는 [IActiveScriptSite](../winscript/reference/iactivescriptsite.md) 인터페이스의 기본 스레드 컨텍스트에서 호스트에서 다음을 수행 하는 경우:  
  
-   기본 스레드 \(메시지 루프를 포함 하는 일반적으로 스레드\)을 선택 합니다.  
  
-   스크립팅 엔진을에서 기본 스레드를 인스턴스화합니다.  
  
-   호출의 경우와 마찬가지로, 특별히 허용 하는 경우를 제외 하 고 엔진 메서드에서 기본 스레드를 스크립팅 [IActiveScript::InterruptScriptThread](../winscript/reference/iactivescript-interruptscriptthread.md) 및 [IActiveScript::Clone](../winscript/reference/iactivescript-clone.md).  
  
-   스크립팅 엔진의 디스패치 개체에는 기본 스레드에서만 호출합니다.  
  
-   창 핸들을 제공 하지 않으면 메시지 루프의 기본 스레드에서 실행 되도록 보장 합니다.  
  
-   호스트의 개체 개체에서에서 기본 스레드 소스 이벤트만 모델이 있습니다.  
  
 이러한 규칙은 모든 호스트가 단일 스레드 자동으로 나옵니다.  위에서 설명한 제한 모델 의도적으로 걸린된 스크립트를 호출 하 여 중단 하는 호스트가 있는 활보 하 고 [IActiveScript::InterruptScriptThread](../winscript/reference/iactivescript-interruptscriptthread.md) \(CTRL \+ BREAK 처리기 또는 같은 시작\) 하 여 다른 스레드에서 또는 스크립트를 사용 하 여 새 스레드를 복제 하려면 [IActiveScript::Clone](../winscript/reference/iactivescript-clone.md).  
  
## 설명  
 있는 자유 스레드된 구현 하도록 선택 하는 호스트에 이러한 제한 사항을 적용 [IActiveScriptSite](../winscript/reference/iactivescriptsite.md) 인터페이스 및 자유 스레드 개체 모델입니다.  이러한 호스트를 사용할 수 있는 [IActiveScript](../winscript/reference/iactivescript.md) 제한 없이 모든 스레드에서 인터페이스.  
  
## 참고 항목  
 [\<PAVE OVER\> Microsoft Windows 스크립트 인터페이스 \- 소개](../Topic/%3CPAVE%20OVER%3E%20Microsoft%20Windows%20Script%20Interfaces%20-%20Introduction.md)