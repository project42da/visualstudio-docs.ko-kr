---
title: "UnInit | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4cd4fc0b-974a-4e61-9ea8-0aaa1a0c52ea
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# UnInit
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

그래픽 로그 파일을 종료하고 응용 프로그램이 그래픽 정보를 기록하는 동안 사용된 리소스를 해제 합니다.  
  
## 구문  
  
```cpp  
void UnInit();  
```  
  
## 설명  
 `VsgDbg` 클래스의 인스턴스가 소멸될 때 `UnInit` 가 자동으로 호출됩니다.  `VsgDbg` 가 그래픽 정보를 기록하고 있지 않은 경우, 이것은 아무런 영향을 주지 않습니다.  
  
 `UnInit` 가 `VsgDbg` 클래스의 인스턴스에서 호출되고 난 후, `Init` 을 호출하여 새로운 그래픽 로그 파일을 만들 수 있고 `UnInit` 를 호출하여 종료할 수 있습니다.  이것을 동일한 `VsgDbg` 인스턴스를 사용하고 싶은 만큼 여러번 반복하여 여러 독립 그래픽 로그 파일을 만들수 있습니다.  
  
## 참고 항목  
 [Init](../debugger/init.md)