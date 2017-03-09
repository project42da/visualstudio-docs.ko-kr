---
title: "CaptureCurrentFrame | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4509311d-6fe2-4b65-9b4a-ff0522585d6a
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# CaptureCurrentFrame
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

그래픽 로그 파일에 현재 프레임의 나머지 부분을 캡처합니다.  
  
## 구문  
  
```cpp  
void CaptureCurrentFrame();  
```  
  
## 설명  
 다른 캡처가 현재 진행 중인 경우 \(예: `BeginCapture` 함수에 의해 시작된 캡처 함수\), 해당 캡처를 완료하고 다른 프레임으로 그래픽 로그에 기록 합니다.  이후에 즉시 그래픽 진단은 개별 프레임으로 기록 되는 현재 프레임의 나머지 부분의 캡처를 시작 합니다.  현재 프레임의 끝은 표시를 호출하여 표시 됩니다.  
  
 프레임을 캡처하기 위해, 캡처 및 그래픽 정보를 기록하는 응용 프로그램을 준비 해야 합니다. 즉, `CaptureCurrentFrame` 을 호출하기 전에 `VsgDbg` 클래스의 인스턴스를 통해 [Init](../debugger/init.md) 을 호출해야 합니다.  
  
## 참고 항목  
 [Init](../debugger/init.md)   
 [BeginCapture](../debugger/begincapture.md)