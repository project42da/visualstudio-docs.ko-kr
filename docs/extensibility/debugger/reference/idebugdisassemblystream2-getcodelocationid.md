---
title: "IDebugDisassemblyStream2::GetCodeLocationId | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugDisassemblyStream2::GetCodeLocationId"
helpviewer_keywords: 
  - "IDebugDisassemblyStream2::GetCodeLocationId"
ms.assetid: 567adfb8-2f54-499a-a027-e4ecb82277ef
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugDisassemblyStream2::GetCodeLocationId
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

특정 코드 컨텍스트에 대해 코드 위치 식별자를 반환합니다.  
  
## 구문  
  
```cpp#  
HRESULT GetCodeLocationId(   
   IDebugCodeContext2* pCodeContext,  
   UINT64*             puCodeLocationId  
);  
```  
  
```c#  
int GetCodeLocationId(   
   IDebugCodeContext2 pCodeContext,  
   out ulong          puCodeLocationId  
);  
```  
  
#### 매개 변수  
 `pCodeContext`  
 \[in\] [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) 을 식별자로 변환할 수 있는 개체입니다.  
  
 `puCodeLocationId`  
 \[out\] 코드 위치 식별자를 반환합니다.  설명 부분을 참조하십시오.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  반환 `E_CODE_CONTEXT_OUT_OF_SCOPE` 코드 컨텍스트가 잘못 되었습니다 있지만 범위 밖에 있습니다.  
  
## 설명  
 코드 위치 식별자 디스어셈블리를 지 원하는 디버그 엔진 \(DE\) 됩니다.  이 위치 식별자는 코드의 위치를 추적 하는 DE에서 내부적으로 사용 됩니다 및 일반적으로 주소 또는 일종의 오프셋입니다.  코드 컨텍스트 위치를 다른 위치에서 코드 컨텍스트에 보다 작으면 해당 코드 위치 식별자의 첫 번째 코드 컨텍스트에 코드 위치 식별자의 두 번째 코드 컨텍스트 미만 이어야 합니다 단이입니다.  
  
 코드 위치 식별자 코드 컨텍스트를 검색 하려면 호출을 [GetCodeContext](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodecontext.md) 메서드.  
  
## 참고 항목  
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)   
 [GetCodeContext](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodecontext.md)