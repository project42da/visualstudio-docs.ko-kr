---
title: "IDebugMethodField::EnumLocals | Microsoft Docs"
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
  - "IDebugMethodField::EnumLocals"
helpviewer_keywords: 
  - "IDebugMethodField::EnumLocals 메서드"
ms.assetid: b0456a6d-2b96-49e2-a871-516571b4f6a5
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugMethodField::EnumLocals
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

선택한 지역 변수에 메서드는 열거자를 만듭니다.  
  
## 구문  
  
```cpp#  
HRESULT EnumLocals(   
   IDebugAddress*     pAddress,  
   IEnumDebugFields** ppLocals  
);  
```  
  
```c#  
int EnumLocals(  
   IDebugAddress        pAddress,   
   out IEnumDebugFields ppLocals  
);  
```  
  
#### 매개 변수  
 `pAddress`  
 \[in\] [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) 컨텍스트 또는 범위의 지역 변수를 얻을 수를 선택 하는 디버그 주소를 나타내는 개체입니다.  
  
 `ppLocals`  
 \[out\] 반환 된 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) ; 지역 변수 목록을 나타내는 개체 그렇지 않으면 지역 없는 경우 null 값을 반환 합니다.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 하거나 없는 지역 없으면 S\_FALSE를 반환 합니다.  그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 지정 된 디버그 주소가 들어 블록 내에서 정의 된 변수만 열거 됩니다.  모든 지역 변수는 컴파일러에서 생성 된 지역 변수를 포함 하 여 필요한 경우 호출 하는 [EnumAllLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumalllocals.md) 메서드.  
  
 메서드에 여러 범위 지정 컨텍스트 또는 블록을 포함할 수 있습니다.  예를 들어, 다음과 같은 인위적인된 방법 세 가지 범위는 두 개의 내부 블록과 메서드 본문이 포함 되어 있습니다.  
  
```c#  
public void func(int index)  
{  
    // Method body scope  
    int a = 0;  
    if (index == 1)  
    {  
        // Inner scope 1  
        int temp1 = a;  
    }  
    else  
    {  
        // Inner scope 2  
        int temp2 = a;  
    }  
}  
```  
  
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md) 나타내는 개체는 `func` 메서드 자체.  호출 하는 `EnumLocals` 메서드를 사용는 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) 설정는 `Inner Scope 1` 주소를 반환 하는 열거형을 포함 하는 `temp1` 예를 들어 변수.  
  
## 참고 항목  
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [EnumAllLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumalllocals.md)