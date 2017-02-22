---
title: "IDebugSymbolProvider::GetMethodFieldsByName | Microsoft Docs"
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
  - "IDebugSymbolProvider::GetMethodFieldsByName"
helpviewer_keywords: 
  - "IDebugSymbolProvider::GetMethodFieldsByName 메서드"
ms.assetid: 1f781320-81ef-4037-b068-f1864b271258
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugSymbolProvider::GetMethodFieldsByName
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드는 정규화 된 메서드 이름을 나타내는 필드를 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetMethodFieldsByName(   
   LPCOLESTR          pszFullName,  
   NAME_MATCH         nameMatch,  
   IEnumDebugFields** ppEnum  
);  
```  
  
```c#  
int GetMethodFieldsByName(  
   string               pszFullName,   
   NAME_MATCH           nameMatch,   
   out IEnumDebugFields ppEnum  
);  
```  
  
#### 매개 변수  
 `pszFullName`  
 \[in\] 메서드 이름입니다.  
  
 `nameMatch`  
 \[in\] 유형을 일치, 대\/소문자 구분을 선택합니다.  
  
 `ppEnum`  
 \[out\] 반환 된 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) 이 메서드와 관련 된 필드에 대 한 열거자입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 오버 하면, 예를 들어 로드 된 경우 메서드가 여러 필드를 함께 연결할 수 있습니다.  
  
## 참고 항목  
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)