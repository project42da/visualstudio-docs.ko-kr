---
title: "IDebugDocumentContext2::Compare | Microsoft Docs"
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
  - "IDebugDocumentContext2::Compare"
helpviewer_keywords: 
  - "IDebugDocumentContext2::Compare"
ms.assetid: 2327b1ba-52d0-42fb-a01e-63cb4b332d2f
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugDocumentContext2::Compare
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

문서 컨텍스트를 지정 된 배열에이 문서 컨텍스트를 비교합니다.  
  
## 구문  
  
```cpp#  
HRESULT Compare(   
   DOCCONTEXT_COMPARE       compare,  
   IDebugDocumentContext2** rgpDocContextSet,  
   DWORD                    dwDocContextSetLen,  
   DWORD*                   pdwDocContext  
);  
```  
  
```c#  
int Compare(   
   enum_ DOCCONTEXT_COMPARE compare,  
   IDebugDocumentContext2[] rgpDocContextSet,  
   uint                     dwDocContextSetLen,  
   out uint                 pdwDocContext  
);  
```  
  
#### 매개 변수  
 `compare`  
 \[in\] 값은 [DOCCONTEXT\_COMPARE](../../../extensibility/debugger/reference/doccontext-compare.md) 비교 형식을 지정 하는 열거형입니다.  
  
 `rgpDocContextSet`  
 \[in\] 배열 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) 를 비교 하 고 있는 문서 컨텍스트를 나타내는 개체입니다.  
  
 `dwDocContextSetLen`  
 \[in\] 비교할 문서 컨텍스트 배열의 길이입니다.  
  
 `pdwDocContext`  
 \[out\] 인덱스를 반환의 `rgpDocContextSet` 의 비교를 만족 시키는 첫 번째 문서의 컨텍스트 배열입니다.  
  
## 반환 값  
 반환 `S_OK` 와 일치 하는 경우.  반환 `S_FALSE` 일치 하는 항목을 찾을 수 없는 경우.  그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) 배열에 전달 되는 개체를 구현 하는 같은 디버그 엔진에서 구현할 수 있는 `IDebugDocumentContext2` ;에서 호출 되는 개체 그렇지 않으면 비교가 잘못 되었습니다.  
  
## 참고 항목  
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)   
 [DOCCONTEXT\_COMPARE](../../../extensibility/debugger/reference/doccontext-compare.md)