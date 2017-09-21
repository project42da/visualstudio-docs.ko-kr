---
title: "IDebugBinder3::GetExceptionObjectAndType | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugBinder3::GetExceptionObjectAndType"
helpviewer_keywords: 
  - "IDebugBinder3::GetExceptionObjectAndType 메서드"
ms.assetid: 2a313fe1-4ee1-4f01-af86-382d6c661a8f
caps.latest.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 7
---
# IDebugBinder3::GetExceptionObjectAndType
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드는 예외 개체와 관련 있는 경우를 검색 합니다.  
  
## 구문  
  
```cpp  
HRESULT GetExceptionObjectAndType(  
   IDebugObject** ppException,  
   IDebugField**  ppField  
);  
```  
  
```c#  
int GetExceptionObjectAndType(  
   out IDebugObject ppException,  
   out IDebugField  ppField  
);  
```  
  
#### 매개 변수  
 `ppException`  
 \[out\] 예외를 나타내는 개체를 반환 합니다.  
  
 `ppField`  
 \[out\] \(Null 값이 될 수 있습니다\) 예외를 일으킨 특정 필드를 나타내는 개체를 반환 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
> [!NOTE]
>  예외 인지 여부를 확인 하 여 반환 값을 확인 합니다. `ppException`: 값이 null 인 경우 예외가이 개체에 연결 됩니다.  
  
## 참고 항목  
 [IDebugBinder3](../../../extensibility/debugger/reference/idebugbinder3.md)