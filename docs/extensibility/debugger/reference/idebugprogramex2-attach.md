---
title: "IDebugProgramEx2::Attach | Microsoft Docs"
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
  - "IDebugProgramEx2::Attach"
helpviewer_keywords: 
  - "IDebugProgramEx2::Attach"
ms.assetid: 33b22b2f-431e-4205-9441-d28a9c928c97
caps.latest.revision: 13
caps.handback.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugProgramEx2::Attach
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

세션을 프로그램에 첨부 합니다.  
  
## 구문  
  
```cpp#  
HRESULT Attach(   
   IDebugEventCallback2* pCallback,  
   DWORD                 dwReason,  
   IDebugSession2*       pSession  
);  
```  
  
```  
[C#]  
int Attach(   
   IDebugEventCallback2 pCallback,  
   uint                 dwReason,  
   IDebugSession2       pSession  
);  
```  
  
#### 매개 변수  
 `pCallback`  
 \[in\] [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 이벤트에 연결 된 디버그 엔진 보내는 콜백 함수를 나타내는 개체입니다.  
  
 `dwReason`  
 \[in\] 값은 [ATTACH\_REASON](../../../extensibility/debugger/reference/attach-reason.md) 는 연결 작업에 대 한 이유를 설명 하는 열거형입니다.  
  
 `pSession`  
 \[in\] 프로그램에 연결 되는 세션에 고유 하 게 식별 하는 값입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  이 메서드는 반환 합니다 `E_ATTACH_DEBUGGER_ALREADY_ATTACHED` 프로그램에 이미 연결 된 경우입니다.  
  
## 설명  
 프로그램에 포함 되어 있는 포트의 값을 사용할 수 있습니다 `pSession` 프로그램에 연결 하려고 하며 세션을 확인 합니다.  예를 들어, 포트를 한 번에 한 프로세스에 연결 하는 하나의 디버그 세션을 허용 하는 경우 포트 같은 세션 프로세스에서 다른 프로그램에 이미 연결 되어 있는지 확인할 수 있습니다.  
  
> [!NOTE]
>  인터페이스에 전달 된 `pSession` 만 쿠키를 연결 하는이 프로그램을 합니다; 디버그 세션 관리자를 고유 하 게 식별 하는 값으로 처리 하는 것 메서드에 제공 된 인터페이스의 기능입니다.  
  
## 참고 항목  
 [IDebugProgramEx2](../../../extensibility/debugger/reference/idebugprogramex2.md)