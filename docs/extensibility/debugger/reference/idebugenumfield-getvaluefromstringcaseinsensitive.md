---
title: "IDebugEnumField::GetValueFromStringCaseInsensitive | Microsoft Docs"
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
  - "IDebugEnumField::GetValueFromStringCaseInsensitive"
helpviewer_keywords: 
  - "IDebugEnumField::GetValueFromStringCaseInsensitive 메서드"
ms.assetid: ef95b38e-d9b2-4fb5-a166-7c2e14641dc7
caps.latest.revision: 8
caps.handback.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugEnumField::GetValueFromStringCaseInsensitive
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드는 대\/소문자 구분 검색을 사용 하 여 열거형 상수의 이름으로 연결 된 값을 반환 합니다.  
  
## 구문  
  
```cpp#  
HRESULT GetValueFromStringCaseInsensitive(  
   LPCOLESTR  pszValue,  
   ULONGLONG* pvalue  
);  
```  
  
```c#  
int GetValueFromStringCaseInsensitive(  
   string    pszValue,   
   out ulong pValue  
);  
```  
  
#### 매개 변수  
 `pszValue`  
 \[in\] 가져올 값의 이름을 지정 하는 문자열입니다.  C \+ \+에 대 한 참고를 와이드 문자의 문자열입니다.  
  
 `pValue`  
 \[out\] 연결 된 숫자 값을 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 반환 `S_FALSE`, 이름을 열거형 또는 오류 코드의 일부가 아닌 경우.  
  
## 설명  
 이 메서드는 대\/소문자 구분입니다.  대\/소문자 구분 검색 \(예를 들어, 이름은 대 소문자를 구분 하는 c \+ \+와 같은 언어\)에 필요 하지 않으면 사용 [GetValueFromString](../../../extensibility/debugger/reference/idebugenumfield-getvaluefromstring.md).  
  
## 참고 항목  
 [IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md)   
 [GetValueFromString](../../../extensibility/debugger/reference/idebugenumfield-getvaluefromstring.md)