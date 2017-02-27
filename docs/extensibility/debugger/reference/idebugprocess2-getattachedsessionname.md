---
title: "IDebugProcess2::GetAttachedSessionName | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProcess2::GetAttachedSessionName"
helpviewer_keywords: 
  - "IDebugProcess2::GetAttachedSessionName"
ms.assetid: 7e5e116f-2c0c-4bc8-ad3f-e9fd2318a7e4
caps.latest.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 13
---
# IDebugProcess2::GetAttachedSessionName
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 프로세스를 디버그 세션의 이름을 가져옵니다.  IDE를 사용자에 게 특정 시스템의 특정 프로세스를 디버깅이 정보를 표시할 수 있습니다.  
  
> [!NOTE]
>  이 메서드는 사용 되지 않습니다, 그리고 및 구현을 항상 반환 해야 `E_NOTIMPL`.  
  
## 구문  
  
```  
HRESULT GetAttachedSessionName(  
   BSTR* pbstrSessionName  
);  
```  
  
#### 매개 변수  
 `pbstrSessionName`  
  
## 반환 값  
 이 메서드는 항상 반환 합니다 `E_NOTIMPL`.  
  
## 참고 항목  
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)