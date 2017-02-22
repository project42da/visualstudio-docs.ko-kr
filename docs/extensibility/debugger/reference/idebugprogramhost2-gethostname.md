---
title: "IDebugProgramHost2::GetHostName | Microsoft Docs"
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
  - "IDebugProgramHost2::GetHostName"
helpviewer_keywords: 
  - "IDebugProgramHost2::GetHostName"
ms.assetid: 48bbb089-e59a-471a-9965-24b42a8dabf3
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugProgramHost2::GetHostName
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

제목, 이름, 또는이 프로그램을 호스팅 프로세스의 파일 이름을 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetHostName(   
   DWORD dwType,  
   BSTR* pbstrHostName  
);  
```  
  
```c#  
int GetHostName(   
   uint dwType,  
   out string pbstrHostName  
);  
```  
  
#### 매개 변수  
 `dwType`  
 \[in\] 값은 [GETHOSTNAME\_TYPE](../../../extensibility/debugger/reference/gethostname-type.md) 열거형입니다.  
  
 `pbstrHostName`  
 \[out\] 호스팅 프로세스는 요청 된 이름을 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이 메서드의 표준 구현에 `dwType` 매개 변수가 무시 되 고 호스트 컴퓨터의 이름을 반환 합니다.  다른 구현 중 전달 하는 것은 `dwType` 매개 변수를 호출 하는 [GetHostName](../../../extensibility/debugger/reference/idebugprogramnode2-gethostname.md) 메서드의 이름을 가져옵니다.  
  
## 참고 항목  
 [IDebugProgramHost2](../../../extensibility/debugger/reference/idebugprogramhost2.md)   
 [GetHostName](../../../extensibility/debugger/reference/idebugprogramnode2-gethostname.md)