---
title: "IDebugProcess2::GetName | Microsoft Docs"
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
  - "IDebugProcess2::GetName"
helpviewer_keywords: 
  - "IDebugProcess2::GetName"
ms.assetid: a2f66ab5-53e5-4cdc-a1b5-3b8afa8ee646
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugProcess2::GetName
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

제목, 이름, 또는 프로세스의 파일 이름을 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetName(   
   GETNAME_TYPE  gnType,  
   BSTR*         pbstrName  
);  
```  
  
```c#  
int GetName(   
   enum_GETNAME_TYPE  gnType,  
   out string         pbstrName  
);  
```  
  
#### 매개 변수  
 `gnType`  
 \[in\] 값은 [GETNAME\_TYPE](../../../extensibility/debugger/reference/getname-type.md) 종류를 반환 하려면 name 속성을 지정 하는 열거형입니다.  
  
 `pbstrName`  
 \[out\] 프로세스의 이름을 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)   
 [GETNAME\_TYPE](../../../extensibility/debugger/reference/getname-type.md)