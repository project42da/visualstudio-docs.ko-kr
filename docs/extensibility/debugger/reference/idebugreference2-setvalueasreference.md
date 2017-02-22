---
title: "IDebugReference2::SetValueAsReference | Microsoft Docs"
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
  - "IDebugReference2::SetValueAsReference"
helpviewer_keywords: 
  - "IDebugReference2::SetValueAsReference"
ms.assetid: 94a545d2-16b9-45e9-b2e7-4e49ff90aad0
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugReference2::SetValueAsReference
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

다른 참조에서 참조의 값을 설정합니다.  다음에 사용하도록 예약됩니다.  
  
## 구문  
  
```cpp#  
HRESULT SetValueAsReference (   
   IDebugReference2** rgpArgs,  
   DWORD              dwArgCount,  
   IDebugReference2*  pValue,  
   DWORD              dwTimeout  
);  
```  
  
```cpp#  
int SetValueAsReference (   
   IDebugReference2[] rgpArgs,  
   uint               dwArgCount,  
   IDebugReference2   pValue,  
   uint               dwTimeout  
);  
```  
  
#### 매개 변수  
 `rgpArgs`  
 \[in\] 배열 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) 개체 참조 값을 설정 하는 방법을 결정 하는 데 사용 됩니다.  
  
 `dwArgCount`  
 \[in\] 배열에 대 한 참조 횟수입니다.  
  
 `pValue`  
 \[in\] [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) 개체에서이 속성 값을 설정 합니다.  
  
 `dwTimeout`  
 \[in\] 이 메서드에서 반환 하기 전에 대기할 시간 \(밀리초\), 최대 시간입니다.  사용 `INFINITE` 무제한으로 대기 합니다.  
  
## 반환 값  
 항상 `E_NOTIMPL`를 반환합니다.  
  
## 참고 항목  
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)