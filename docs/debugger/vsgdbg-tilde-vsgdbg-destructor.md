---
title: "VsgDbg::~VsgDbg(소멸자) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7a3b97fb-d344-4df7-b195-9347d1edfcf7
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# VsgDbg::~VsgDbg(소멸자)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

`VsgDbg` 클래스의 인스턴스를 제거합니다.  그래픽 정보가 기록되고 있는 경우, 그래픽 로그 파일이 종료되고 닫히며, 그래픽 정보를 캡처하는 동안 사용된 리소스가 해제됩니다.  
  
## 구문  
  
```cpp  
~VsgDbg();  
```  
  
## 참고 항목  
 [VsgDbg::VsgDbg\(생성자\)](../debugger/vsgdbg-vsgdbg-constructor.md)