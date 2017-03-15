---
title: "ToggleHUD | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7261e01d-3c72-46ce-9fb3-5f33b2ddb901
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# ToggleHUD
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

그래픽 진단 *HUD* \(Head\-Up Display\) 오버레이를 사용 또는 해제 합니다.  
  
## 구문  
  
```cpp  
void ToggleHUD();  
```  
  
## 설명  
 그래픽 진단 HUD가 그래픽 진단이 실행 되는 응용 프로그램의 왼쪽 위 모서리에 표시 됩니다.  이것은 응용 프로그램 및 런타임 정보 캡처에 대한 런타임 정보를 표시하고, [AddMessage](../debugger/addmessage.md) 멤버 함수 호출로 인해 추가된 메시지를 보여줍니다.  
  
 HUD을 전환하기 위해, 그래픽 정보를 적극적으로 캡처할 필요가 없습니다. `VsgDbg` 클래스의 인스턴스를 통해 전환될 수 있고, [Init](../debugger/init.md) 멤버 함수는 처음에 호출 될 필요가 없습니다.