---
title: "IDebugDocument2::GetName | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugDocument2::GetName"
helpviewer_keywords: 
  - "IDebugDocument2::GetName"
ms.assetid: 6f09ff09-b0cf-4472-8fc8-143991f0ceb1
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugDocument2::GetName
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

문서의 이름을 여러 형태 중 하나에서 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetName(   
   GETNAME_TYPE gnType,  
   BSTR*        pbstrFileName  
);  
```  
  
```c#  
int GetName(   
   enum_GETNAME_TYPE gnType,  
   out string        pbstrFileName  
);  
```  
  
#### 매개 변수  
 `gnType`  
 \[in\] 값은 [GETNAME\_TYPE](../../../extensibility/debugger/reference/getname-type.md) 종류를 반환 하려면 name 속성을 결정 하는 열거형입니다.  
  
 `pbstrFileName`  
 \[out\] 문서 이름이 들어 있는 문자열을 반환 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이 메서드는 예를 들어, 제목이 나 파일 이름 또는 파일 이름에도 일부 문서의 이름을 반환할 수 있습니다.  
  
## 참고 항목  
 [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)   
 [GETNAME\_TYPE](../../../extensibility/debugger/reference/getname-type.md)