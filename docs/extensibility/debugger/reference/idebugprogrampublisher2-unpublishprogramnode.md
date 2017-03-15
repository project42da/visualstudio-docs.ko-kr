---
title: "IDebugProgramPublisher2::UnpublishProgramNode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProgramPublisher2::UnpublishProgramNode"
helpviewer_keywords: 
  - "IDebugProgramPublisher2::UnpublishProgramNode"
ms.assetid: 57c7e6e1-b84e-4e14-ad83-cbbb64e2f526
caps.latest.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugProgramPublisher2::UnpublishProgramNode
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

지정한 프로그램 노드 가용성에서 디버그 엔진 \(DEs\) 및 세션 디버그 매니저 \(SDM\)을 제거 합니다.  
  
## 구문  
  
```cpp  
HRESULT UnpublishProgramNode(  
   IDebugProgramNode2* pProgramNode  
);  
```  
  
```c#  
int UnpublishProgramNode(  
   IDebugProgramNode2 pProgramNode  
);  
```  
  
#### 매개 변수  
 `pProgramNode`  
 \[in\] [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) 제거 하는 프로그램이 노드를 나타내는 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 프로그램 노드 제거 후에 더 이상 프로그램 정보를 쿼리 하는 사용할 수 없습니다.  
  
 프로그램 노드에서 사용할 수 있게 하려면 호출 하는 [PublishProgramNode](../../../extensibility/debugger/reference/idebugprogrampublisher2-publishprogramnode.md) 메서드.  
  
## 참고 항목  
 [IDebugProgramPublisher2](../../../extensibility/debugger/reference/idebugprogrampublisher2.md)   
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [PublishProgramNode](../../../extensibility/debugger/reference/idebugprogrampublisher2-publishprogramnode.md)