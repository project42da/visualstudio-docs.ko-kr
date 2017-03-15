---
title: "IDebugMethodField::EnumParameters | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugMethodField::EnumParameters"
helpviewer_keywords: 
  - "IDebugMethodField::EnumParameters 메서드"
ms.assetid: d77b1197-deb6-4144-8d1b-8b09949ccfac
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugMethodField::EnumParameters
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

메서드의 매개 변수에 대 한 열거자를 만듭니다.  
  
## 구문  
  
```cpp#  
HRESULT EnumParameters(   
   IEnumDebugFields** ppParams  
);  
```  
  
```c#  
int EnumParameters(  
   out IEnumDebugFields ppParams  
);  
```  
  
#### 매개 변수  
 `ppParams`  
 \[out\] 반환 된 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) ; 메서드에 매개 변수 목록을 나타내는 개체 그렇지 않으면 매개 변수가 없는 경우 null 값을 반환 합니다.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 또는 매개 변수가 없으면 S\_FALSE를 반환 합니다.  그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 각 요소는 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 서로 다른 매개 변수를 나타내는 개체입니다.  호출 하는 [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) 정확 하 게 어떤 종류의 매개 변수 개체를 나타내는지 확인 하려면 각 개체에 메서드를.  
  
 매개 변수 이름 및 해당 형식 모두 포함 되어 있습니다.  클래스 메서드의 첫 번째 매개 변수는 일반적으로 "this"이 포인터입니다.  
  
 형식 매개 변수가 필요한 경우에 호출 하 여 [EnumArguments](../../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md) 메서드.  
  
## 참고 항목  
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [EnumArguments](../../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md)