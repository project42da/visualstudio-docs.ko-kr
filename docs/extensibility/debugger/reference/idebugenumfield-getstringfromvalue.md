---
title: "IDebugEnumField::GetStringFromValue | Microsoft Docs"
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
  - "IDebugEnumField::GetStringFromValue"
helpviewer_keywords: 
  - "IDebugEnumField::GetStringFromValue 메서드"
ms.assetid: 5f95fd0c-fdce-497f-9f54-2ad8749494e9
caps.latest.revision: 5
caps.handback.revision: 5
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugEnumField::GetStringFromValue
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드는 열거형 상수 값을 지정 된 이름을 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetStringFromValue(  
   ULONGLONG value,  
   BSTR*     pbstrValue  
);  
```  
  
```c#  
int GetStringFromValue(  
   ulong      value,  
   out string pbstrValue  
);  
```  
  
#### 매개 변수  
 `value`  
 \[in\] 열거형의 이름 상수 발생 값입니다.  
  
 `pbstrValue`  
 \[out\] 열거형 상수를 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 반환 `S_FALSE` 값 이름이 없습니다 관련 된 경우 오류 코드를 반환 합니다.  
  
## 설명  
 열거형에 정의 된 이름은 동일한 값과 관련 된 이름을 두 개 이상 있으면 반환 됩니다.  
  
## 참고 항목  
 [IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md)