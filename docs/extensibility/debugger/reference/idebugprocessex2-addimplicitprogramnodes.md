---
title: "IDebugProcessEx2::AddImplicitProgramNodes | Microsoft Docs"
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
  - "IDebugProcessEx2::AddImplicitProgramNodes"
helpviewer_keywords: 
  - "IDebugProcessEx2::AddImplicitProgramNodes 메서드"
ms.assetid: 8b491b00-f9e7-45b3-9115-fe58c3464289
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugProcessEx2::AddImplicitProgramNodes
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드는 프로그램 노드가 지정 된 각 디버그 엔진 \(DE\) 추가 합니다.  
  
## 구문  
  
```cpp#  
HRESULT AddImplicitProgramNodes(  
   REFGUID guidLaunchingEngine,  
   GUID*   rgguidSpecificEngines,  
   DWORD   celtSpecificEngines  
);  
```  
  
```c#  
int AddImplicitProgramNodes(  
   ref Guid guidLaunchingEngine,  
   Guid[]   rgguidSpecificEngines,  
   uint     celtSpecificEngines  
);  
```  
  
#### 매개 변수  
 `guidLaunchingEngine`  
 \[in\] `GUID` 의 프로그램을 실행 하는 데 사용 됩니다 \(및 자체 프로그램에 노드를 추가 하려면 가정\) 하는 DE.  
  
 `rgguidSpecificEngines`  
 \[in\] 배열 `GUID`s DEs 응용 프로그램 노드가 추가 될 것입니다.  
  
 `celtSpecificEngines`  
 \[in\] 수를 `GUID`s에 있는 `rgguidSpecificEngines` 배열.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 [프로그램 노드](../../../extensibility/debugger/program-nodes.md)나열 된 각 DE에 대 한 추가 됩니다 `rgguidSpecificEngines`\-시작 엔진을 제외 \(지정 `guidLaunchingEngine`\), 가정 프로그램을 시작 하면 해당 프로그램이 노드를 추가 합니다.  
  
## 참고 항목  
 [IDebugProgramEx2](../../../extensibility/debugger/reference/idebugprogramex2.md)   
 [프로그램 노드](../../../extensibility/debugger/program-nodes.md)