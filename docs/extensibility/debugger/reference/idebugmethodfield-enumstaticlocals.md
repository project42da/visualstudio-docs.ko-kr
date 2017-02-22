---
title: "IDebugMethodField::EnumStaticLocals | Microsoft Docs"
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
  - "IDebugMethodField::EnumStaticLocals"
helpviewer_keywords: 
  - "IDebugMethodField::EnumStaticLocals 메서드"
ms.assetid: e0c522c4-f759-4c32-ae87-7abcb573e77d
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugMethodField::EnumStaticLocals
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

정적 지역 변수는 메서드에 대 한 열거자를 만듭니다.  
  
## 구문  
  
```cpp#  
HRESULT EnumStaticLocals(   
   IEnumDebugFields** ppLocals  
);  
```  
  
```c#  
int EnumStaticLocals(  
   out IEnumDebugFields ppLocals  
);  
```  
  
#### 매개 변수  
 `ppLocals`  
 \[out\] 반환 된 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) 목록에 정적 지역 변수를 나타내는 개체입니다.  없는 정적 지역 변수 이면 null 값을 반환 합니다.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 하거나 없는 정적 지역 변수 없으면 S\_FALSE를 반환 합니다.  그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 각 요소는 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 서로 다른 정적 지역 변수를 나타내는 개체입니다.  호출 하는 [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) 정확 하 게 어떤 종류의 정적 로컬 개체를 나타내는지 확인 하려면 각 개체에 메서드를.  
  
## 참고 항목  
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)