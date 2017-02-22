---
title: "IDebugProperty2::SetValueAsString | Microsoft Docs"
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
  - "IDebugProperty2::SetValueAsString"
helpviewer_keywords: 
  - "IDebugProperty2::SetValueAsString"
ms.assetid: 9e6a5054-41b7-4223-b509-b93689d366a5
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugProperty2::SetValueAsString
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

지정 된 문자열에서 속성의 값을 설정합니다.  
  
## 구문  
  
```cpp#  
HRESULT SetValueAsString (   
   LPCOLESTR pszValue,  
   UINT      nRadix,  
   DWORD     dwTimeout  
);  
```  
  
```c#  
int SetValueAsString (   
   string pszValue,  
   uint   nRadix,  
   uint   dwTimeout  
);  
```  
  
#### 매개 변수  
 `pszValue`  
 \[in\] 설정 해야 하는 값을 포함 하는 문자열입니다.  
  
 `nRadix`  
 \[in\] 모든 숫자 정보를 해석 하는 데 사용할 기 수입니다.  기 수를 자동으로 확인 하도록 시도 하는 0입니다.  
  
 `dwTimeout`  
 \[in\] 이 메서드에서 반환 하기 전에 대기할 시간 \(밀리초\), 최대 시간을 지정 합니다.  사용 `INFINITE` 무제한으로 대기 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환합니다.  다른 가능한 값은 다음과 같습니다.  
  
|값|설명|  
|-------|--------|  
|`E_SETVALUE_VALUE_CANNOT_BE_SET`|문자열을 속성 값으로 변환할 수 없습니다 또는 속성 값을 설정할 수 없습니다.|  
|`E_SETVALUE_VALUE_IS_READONLY`|속성이 읽기 전용입니다.|  
  
## 참고 항목  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)