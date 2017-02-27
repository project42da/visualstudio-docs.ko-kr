---
title: "IDebugProgramNode2::GetEngineInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProgramNode2::GetEngineInfo"
helpviewer_keywords: 
  - "IDebugProgramNode2::GetEngineInfo"
ms.assetid: 664e7fe5-9100-4b7d-9dc5-e5a4dd0d0451
caps.latest.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 13
---
# IDebugProgramNode2::GetEngineInfo
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이름 및 프로그램을 실행 하 여 디버그 엔진 \(DE\)의 식별자를 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetEngineInfo (   
   BSTR* pbstrEngine,  
   GUID* pguidEngine  
);  
```  
  
```c#  
int GetEngineInfo(  
   out string pbstrEngine,   
   out Guid pguidEngine  
);  
```  
  
#### 매개 변수  
 `pbstrEngine`  
 \[out\] 프로그램을 실행 하는 DE 이름을 반환 \(c \+ \+ 관련:이 호출자에 게 엔진 이름에 관심이 없음을 나타내는 null 포인터를 수 있습니다\).  
  
 `pguidEngine`  
 \[out\] 프로그램을 실행 하는 DE의 전역 고유 식별자를 반환 \(c \+ \+ 관련:이 호출자가 엔진의 GUID에 관심이 없음을 나타내는 null 포인터를 수 있습니다\).  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)