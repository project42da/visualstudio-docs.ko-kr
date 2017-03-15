---
title: "IDebugBreakpointChecksumRequest2::IsChecksumEnabled | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDebugBreakpointChecksumRequest2::IsChecksumEnabled"
ms.assetid: 8b1853b5-745c-4cd6-88a9-ce0673971bb0
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IDebugBreakpointChecksumRequest2::IsChecksumEnabled
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 문서에 대 한 체크섬을 사용할 수 있는지 여부를 결정 합니다.  
  
## 구문  
  
```cpp#  
HRESULT IsChecksumEnabled(   
   BOOL *pfChecksumEnabled  
);  
```  
  
```c#  
public int IsChecksumEnabled(   
   out int pfChecksumEnabled  
);  
```  
  
#### 매개 변수  
 `pfChecksumEnabled`  
 \[out\] 검사 값을 사용 하는 경우 TRUE를 반환 합니다. 그렇지 않은 경우 FALSE를 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDebugBreakpointChecksumRequest2](../../../extensibility/debugger/reference/idebugbreakpointchecksumrequest2.md)