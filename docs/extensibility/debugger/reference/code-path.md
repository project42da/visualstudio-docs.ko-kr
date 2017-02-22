---
title: "CODE_PATH | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CODE_PATH"
helpviewer_keywords: 
  - "CODE_PATH 구조"
ms.assetid: 2d4b2890-4c9d-47e1-83c0-df9c6436427f
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# CODE_PATH
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

메서드 또는 함수 호출에 설명 합니다.  
  
## 구문  
  
```cpp#  
typedef struct tagCODE_PATH {   
   BSTR                bstrName;  
   IDebugCodeContext2* pCode;  
} CODE_PATH;  
```  
  
```c#  
public struct CODE_PATH {  
   public string            bstrName;  
   public IDebugCodeContext pCode;  
}  
```  
  
## Members  
 bstrName  
 코드 경로의 이름입니다.  
  
 pCode  
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) 함수를 실행 하는 코드 부분을 식별 하는 개체입니다.  
  
## 설명  
 이 구조를 사용 하 여 함수를 한 단계씩 실행을 구현 합니다.  [EnumCodePaths](../../../extensibility/debugger/reference/idebugprogram2-enumcodepaths.md)디버깅 중인 프로그램에 현재 위치에서 모든 전화를 반환 합니다.  이 구조와 같은 하나의 통화를 나타냅니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)   
 [EnumCodePaths](../../../extensibility/debugger/reference/idebugprogram2-enumcodepaths.md)