---
title: "포인터가 메모리 주소를 손상시키는지 어떻게 알 수 있습니까? | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
  - "C++"
helpviewer_keywords: 
  - "주소, 메모리 주소를 손상시키는 포인터"
  - "손상된 메모리 주소"
  - "디버깅[C++], 메모리 손상"
  - "포인터에 의한 메모리 주소 손상"
  - "메모리, 손상"
  - "포인터, 메모리 주소 손상"
ms.assetid: a147c939-4fb1-415c-8410-cf303781e9e8
caps.latest.revision: 19
caps.handback.revision: 19
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 포인터가 메모리 주소를 손상시키는지 어떻게 알 수 있습니까?
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

## 문제 설명  
 포인터 하나가 0x00408000 주소의 메모리를 손상시키고 있는 것 같습니다.  어떻게 알아 낼 수 있습니까?  
  
## 해결책  
  
#### 힙 손상 확인  
  
-   대부분의 메모리 손상은 실제로 힙 손상으로 인해 발생합니다.  전역 플래그 유틸리티\(gflags.exe\) 또는 pageheap.exe를 사용해 보십시오.  [http:\/\/support.microsoft.com\/default.aspx?scid\=kb;en\-us;286470](http://support.microsoft.com/default.aspx?scid=kb;en-us;286470)을 참조하십시오.  
  
#### 메모리 주소가 수정된 위치를 찾으려면  
  
1.  0x00408000에 데이터 중단점을 설정합니다.  [데이터 변경 중단점 설정\(네이티브 C\+\+만 해당\)](../debugger/using-breakpoints.md#BKMK_Set_a_data_change_breakpoint__native_C___only_)을 참조하십시오.  
  
2.  중단점이 적중되면 **메모리** 창을 사용하여 0x00408000에서 시작하는 메모리 내용을 검토합니다.  자세한 내용은 [메모리 창](../debugger/memory-windows.md)을 참조하십시오.  
  
## 참고 항목  
 [네이티브 코드 디버깅 FAQ](../debugger/debugging-native-code-faqs.md)   
 [네이티브 코드 디버깅](../debugger/debugging-native-code.md)