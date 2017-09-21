---
title: "DisplayKind | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "DisplayKind 열거형"
ms.assetid: 940968c5-6065-4bda-8ee6-c31597db4d71
caps.latest.revision: 5
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 5
---
# DisplayKind
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

열거를 사용 하는 정보 종류를 나타내는 유효한 값은 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 개체 및 사용자에 게 표시 합니다.  
  
## 구문  
  
```cpp#  
enum enum_DisplayKind  
{  
   DisplayKind_Value = 0x1,  
   DisplayKind_Name = 0x2,  
   DisplayKind_Type = 0x3,  
};  
typedef DWORD DisplayKind;  
```  
  
```c#  
public enum enum_DisplayKind  
{  
   DisplayKind_Value = 0x1,  
   DisplayKind_Name = 0x2,  
   DisplayKind_Type = 0x3,  
};  
```  
  
#### 매개 변수  
 DisplayKind\_Value  
 필드의 값입니다.  
  
 DisplayKind\_Name  
 필드의 이름입니다.  
  
 DisplayKind\_Type  
 필드의 형식입니다.  
  
## 요구 사항  
 헤더: Ee.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetValueDisplayStringCount](../../../extensibility/debugger/reference/ieevisualizerservice-getvaluedisplaystringcount.md)