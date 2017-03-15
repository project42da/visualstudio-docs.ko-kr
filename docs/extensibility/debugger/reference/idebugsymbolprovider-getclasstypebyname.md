---
title: "IDebugSymbolProvider::GetClassTypeByName | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugSymbolProvider::GetClassTypeByName"
helpviewer_keywords: 
  - "IDebugSymbolProvider::GetClassTypeByName 메서드"
ms.assetid: 2c748909-51dc-49b7-b193-19f96fca1138
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IDebugSymbolProvider::GetClassTypeByName
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드는 정규화 된 클래스 이름을 나타내는 클래스 필드 형식을 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetClassTypeByName(   
   LPCOLESTR          pszClassName,  
   NAME_MATCH         nameMatch,  
   IDebugClassField** ppField  
);  
```  
  
```c#  
int GetClassTypeByName(  
   string               pszClassName,   
   NAME_MATCH           nameMatch,   
   out IDebugClassField ppField  
);  
```  
  
#### 매개 변수  
 `pszClassName`  
 \[in\] 클래스 이름입니다.  
  
 `nameMatch`  
 \[in\] 유형을 일치, 대\/소문자 구분을 선택합니다.  [NAME\_MATCH](../../../extensibility/debugger/reference/name-match.md) 열거형의 값입니다.  
  
 `ppField`  
 \[out\] 클래스 형식을 나타내는 반환의 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md) 인터페이스입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [NAME\_MATCH](../../../extensibility/debugger/reference/name-match.md)   
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)