---
title: "JsDebugReadMemoryFlags 열거형 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: JsDebugReadMemoryFlags
apilocation: jscript9diag.dll
ms.assetid: 0d98d154-9cb1-49de-b2df-a2d029d343b7
caps.latest.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 5
---
# JsDebugReadMemoryFlags 열거형
메모리를 읽을 때의 동작을 지정하는 플래그입니다.  
  
## 구문  
  
```  
enum JsDebugReadMemoryFlags  
{  
   None = 0,  
   JsDebugAllowPartialRead= 0x1  
} JsDebugReadMemoryFlags;  
```  
  
## Members  
  
### 값  
  
|이름|설명|  
|--------|--------|  
|`JsDebugAllowPartialRead`|메모리 일부의 읽기만 성공한 경우 호출자가 읽기 작업을 성공하도록 하려는 것을 나타냅니다.  이것을 설정하면 '주소'사 잘못된 경우 E\_JsDEBUG\_INVALID\_MEMORY\_ADDRESS 오류만 발생합니다.  이 플래그가 분명한 경우 요청한 메모리 일부를 읽을 수 없으면 E\_JsDEBUG\_INVALID\_MEMORY\_ADDRESS 오류가 발생됩니다.|  
|`None`|호출자가 ReadMemory에 대한 기본 동작을 원한다는 것을 나타냅니다.|  
  
## 요구 사항  
 **헤더:** jscript9diag.h  
  
## 참고 항목  
 [Windows 스크립트 인터페이스 참조](../../winscript/reference/windows-script-interfaces-reference.md)