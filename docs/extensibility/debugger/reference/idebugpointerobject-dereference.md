---
title: "IDebugPointerObject::Dereference | Microsoft Docs"
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
  - "IDebugPointerObject::Dereference"
helpviewer_keywords: 
  - "IDebugPointerObject::Dereference 메서드"
ms.assetid: 196ec2cc-8569-4780-b217-23b24e7f50ca
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugPointerObject::Dereference
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

가리키는 개체를 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT DeReference(   
   DWORD          dwIndex,  
   IDebugObject** ppObject  
);  
```  
  
```c#  
int Dereference(  
   uint             dwIndex,   
   out IDebugObject ppObject  
);  
```  
  
#### 매개 변수  
 `dwIndex`  
 \[in\] 개체의 시작 부분에서의 단순한 바이트 오프셋에 가리키는.  
  
 `ppObject`  
 \[out\] 반환 된 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 있는 경우를 가리키는 더한 오프셋, 개체를 나타내는 개체입니다.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환 합니다.  이 개체가 다른 개체를 가리키지 않는 경우 E\_FAIL을 반환 합니다.  
  
## 설명  
 개체를 가리키는 기본 형식 또는 형식 클래스 또는 구조체와 같은 더 복잡 한 될 수 있습니다.  
  
## 참고 항목  
 [IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md)