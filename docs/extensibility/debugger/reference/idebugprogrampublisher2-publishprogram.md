---
title: "IDebugProgramPublisher2::PublishProgram | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProgramPublisher2::PublishProgram"
helpviewer_keywords: 
  - "IDebugProgramPublisher2::PublishProgram"
ms.assetid: 92ff63f0-e869-4040-b3ae-b2c899e708ff
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IDebugProgramPublisher2::PublishProgram
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드는 디버그 세션 관리자 및 프로그램 디버그 엔진 \(DEs\)을 사용할 수 있습니다.  
  
## 구문  
  
```cpp  
HRESULT PublishProgram(  
   CONST_GUID_ARRAY Engines,  
   LPCOLESTR        szFriendlyName,  
   IUnknown*        pDebuggeeInterface  
);  
```  
  
```c#  
int PublishProgram(  
   CONST_GUID_ARRAY Engines,  
   string           szFriendlyName,  
   object           pDebuggeeInterface  
);  
```  
  
#### 매개 변수  
 `Engines`  
 \[in\] 시작 하거나이 프로그램에 연결 하는 Guid Des의 배열입니다.  
  
 `szFriendlyName`  
 \[in\] \(메뉴 또는 대화 상자는 사용자에 게 표시\)는 프로그램 이름입니다.  
  
 `pDebuggeeInterface`  
 \[in\] `IUnknown` 프로그램에 대 한 인터페이스 \(이 값으로 쿠키; 프로그램을 고유 하 게 식별을 사용 합니다 이 같은 값을 사용 하 여 "프로그램 게시를 취소 하려면"\)  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 디버깅에 대 한 더 이상 사용할 수 있도록 하려면 호출 [UnpublishProgram](../../../extensibility/debugger/reference/idebugprogrampublisher2-unpublishprogram.md).  
  
## 참고 항목  
 [IDebugProgramPublisher2](../../../extensibility/debugger/reference/idebugprogrampublisher2.md)   
 [UnpublishProgram](../../../extensibility/debugger/reference/idebugprogrampublisher2-unpublishprogram.md)