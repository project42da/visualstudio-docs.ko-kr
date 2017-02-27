---
title: "IDebugMethodField::EnumAllLocals | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugMethodField::EnumAllLocals"
helpviewer_keywords: 
  - "IDebugMethodField::EnumAllLocals 메서드"
ms.assetid: 0bc7cc13-2628-4bd8-8c06-4d2aa6755ea8
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IDebugMethodField::EnumAllLocals
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

메서드를 내부적으로 컴파일러에 의해 생성 된 포함 한 모든 지역 변수에 대 한 열거자를 만듭니다.  
  
## 구문  
  
```cpp#  
HRESULT EnumAllLocals(   
   IDebugAddress*     pAddress,  
   IEnumDebugFields** ppLocals  
);  
```  
  
```c#  
int EnumAllLocals(  
   IDebugAddress        pAddress,   
   out IEnumDebugFields ppLocals  
);  
```  
  
#### 매개 변수  
 `pAddress`  
 \[in\] [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) 특정 범위나 컨텍스트를 가리키는 메서드 내에서 디버그 주소를 나타내는 개체입니다.  
  
 `ppLocals`  
 \[out\] 반환 된 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) 입니다; 지정 된 범위에 모든 지역 변수 목록을 나타내는 개체 그렇지 않으면 없는 지역 변수를 나타내는 null 값을 반환 합니다.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 하거나 없는 지역 없으면 S\_FALSE를 반환 합니다.  그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 지정 된 디버그 주소가 들어 블록 내에서 정의 된 변수만 열거 됩니다.  이 메서드는 컴파일러에서 생성 된 지역 변수를 포함합니다.  명시적으로 호출 소스에 정의 된 지역 변수는 데 경우에 [EnumLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumlocals.md) 메서드.  
  
 메서드에 여러 범위 지정 컨텍스트 또는 블록을 포함할 수 있습니다.  
  
## 참고 항목  
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [EnumLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumlocals.md)