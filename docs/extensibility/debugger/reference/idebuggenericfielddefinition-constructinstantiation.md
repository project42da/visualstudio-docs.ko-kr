---
title: "IDebugGenericFieldDefinition::ConstructInstantiation | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ConstructInstantiation"
  - "IDebugGenericFieldDefinition::ConstructInstantiation"
ms.assetid: ef8ae261-a98b-4dc2-93b3-7c5191818ba2
caps.latest.revision: 8
caps.handback.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugGenericFieldDefinition::ConstructInstantiation
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

형식 인수의 배열을 지정 하 여 필드 인스턴스를 생성 합니다.  
  
## 구문  
  
```cpp#  
HRESULT ConstructInstantiation(  
   ULONG32       cArgs,  
   IDebugField** ppArgs,  
   IDebugField** ppConstructedField  
);  
```  
  
```c#  
int ConstructInstantiation(  
   uint            cArgs,  
   IDebugField[]   ppArgs,  
   out IDebugField ppConstructedField  
);  
```  
  
#### 매개 변수  
 `cArgs`  
 \[in\] 인수 개수는 `ppArgs` 배열입니다.  
  
 `ppArgs`  
 \[in\] 형식 인수가 들어 있는 배열입니다.  형식 인수 \(비 제네릭 또는 완전히 인스턴스화된 제네릭\) 닫힌된 형식 이어야 합니다.  
  
 `ppConstructedField`  
 \[out\] 반환은 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 의 새 필드를 나타내는 인터페이스입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 제약 조건이 검사 되지 않습니다.  
  
## 참고 항목  
 [IDebugGenericFieldDefinition](../../../extensibility/debugger/reference/idebuggenericfielddefinition.md)