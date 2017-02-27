---
title: "IDebugCodeContext2::GetDocumentContext | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugCodeContext2::GetDocumentContext"
helpviewer_keywords: 
  - "IDebugCodeContext2::GetDocumentContext"
ms.assetid: d552cc92-963f-43c1-949f-ae6b63a427b8
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IDebugCodeContext2::GetDocumentContext
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 코드 컨텍스트에 해당 문서 컨텍스트를 가져옵니다.  문서 컨텍스트가이 명령이 생성 되는 소스 코드에 해당 하는 소스 파일의 위치를 나타냅니다.  
  
## 구문  
  
```cpp#  
HRESULT GetDocumentContext(   
   IDebugDocumentContext2** ppSrcCxt  
);  
```  
  
```c#  
int GetDocumentContext(   
   out IDebugDocumentContext2 ppSrcCxt  
);  
```  
  
#### 매개 변수  
 `ppSrcCxt`  
 \[out\] 반환은 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) 에서 코드 컨텍스트에 해당 하는 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 코드 컨텍스트 위치를 코드 명령 실행 스트림에 있는 동안 일반적으로 문서의 컨텍스트의 소스 파일에서 위치 이름으로 생각할 수 있습니다.  
  
## 참고 항목  
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)   
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)