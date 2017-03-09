---
title: "BeginCapture | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9edbb52d-ee0b-4cc4-a382-972bcee067d3
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# BeginCapture
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

`EndCapture` 로 끝나는 캡처 간격이 시작됩니다.  
  
## 구문  
  
```cpp  
void BeginCapture();  
```  
  
## 설명  
 캡처 간격은 일반적으로 한 프레임의 하위 집합에 확장됩니다. \(예: 그래픽 정보를 오직 일정량의 그리기 호출만큼만 캡처하고 싶을 경우\)  캡처 간격이 표시하기 위해 호출에 걸친 경우, 두 프레임의 그래픽 정보가 캡처됩니다.  첫 번째 프레임의은 `BeginCapture` 호출과 표시하기 위한 호출에 걸칩니다. 두 번째 프레임은 표시하기 위한 호출 후의 첫 번째 Direct3D 이벤트 및 `EndCapture` 호출 간의 간격에 걸칩니다.  
  
 간격을 캡처하기 위해, 캡처 및 그래픽 정보를 기록하는 응용 프로그램을 준비 해야 합니다. 즉, `BeginCapture` 또는 `EndCapture` 을 호출하기 전에 `VsgDbg` 클래스의 인스턴스를 통해 [Init](../debugger/init.md) 을 호출해야 합니다.  
  
## 참고 항목  
 [EndCapture](../debugger/endcapture.md)   
 [CaptureCurrentFrame](../debugger/capturecurrentframe.md)