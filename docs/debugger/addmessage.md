---
title: "AddMessage | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 102a0404-a00c-4566-93f3-01bc8df63280
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# AddMessage
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

그래픽 진단 *HUD* \(Head\-Up Display\) 에 사용자 지정 메시지를 추가합니다.  
  
## 구문  
  
```cpp  
void AddMessage(  
  wchar_t const * szMessage  
);  
```  
  
#### 매개 변수  
 `szMessage`  
 HUD에 추가할 메시지입니다.  
  
## 설명  
 그래픽 진단 HUD가 그래픽 진단이 실행 되는 응용 프로그램의 왼쪽 위 모서리에 표시 됩니다.  이것은 응용 프로그램 및 런타임 정보 캡처에 대한 런타임 정보를 표시하고, 이 함수 호출로 인해 추가된 메시지를 보여줍니다.  
  
 메시지를 HUD에 추가하기 위해, 그래픽 정보를 적극적으로 캡처할 필요가 없습니다. `VsgDbg` 클래스의 인스턴스를 통해 메시지를 추가할 수 있지만 [Init](../debugger/init.md) 멤버 함수가 먼저 호출될 필요는 없습니다.  메시지는 HUD에만 표시 되지만, 그래픽 로그 파일에 기록 되지 않습니다.