---
title: "IDebugProcessSecurity::GetUserName | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDebugProcessSecurity::GetUserName"
ms.assetid: c73c60ac-da6e-45ae-8f04-95353a24ca3e
caps.latest.revision: 4
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 4
---
# IDebugProcessSecurity::GetUserName
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

사용자 이름을 포트 공급자에서 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetUserName(  
    BSTR *pbstrUserName  
);  
```  
  
```c#  
int GetUserName (  
    string pbstrUserName  
);  
```  
  
#### 매개 변수  
 `pbstrUserName`  
 \[out\] 사용자 이름이 포함 된 문자열입니다.  
  
## 반환 값  
 메서드가 성공 하면, 반환 `S_OK`.  그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 `GetUserName`표시 되는 사용자 이름을 반환 하는  **사용자 이름** 의 열은  **프로세스에 연결** 대화 상자.  볼 수는  **프로세스에 연결** 대화 상자를 클릭  **프로세스에 연결** 에  **도구** 메뉴에는 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] 통합된 개발 환경 \(IDE\)입니다.  
  
## 참고 항목  
 [IDebugProcessSecurity](../../../extensibility/debugger/reference/idebugprocesssecurity.md)