---
title: "IDebugAlias2::GetAppDomainId | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "GetAppDomainId"
  - "IDebugAlias2::GetAppDomainId"
ms.assetid: 23581aaa-5a53-4859-b264-eca49fc44bcd
caps.latest.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugAlias2::GetAppDomainId
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

응용 프로그램 도메인의 식별자를 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT GetAppDomainId (  
   ULONG32* pappDomainId  
);  
```  
  
```c#  
int GetAppDomainId (  
   out uint pappDomainId  
);  
```  
  
#### 매개 변수  
 `pappDomainId`  
 \[out\] 응용 프로그램 도메인 식별자를 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 응용 프로그램을 다시 시작할 때마다 응용 프로그램 도메인 식별자 변경 및 새 응용 프로그램 도메인이 만들어집니다.  
  
## 참고 항목  
 [IDebugAlias2](../../../extensibility/debugger/reference/idebugalias2.md)