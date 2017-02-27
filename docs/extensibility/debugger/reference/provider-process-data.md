---
title: "PROVIDER_PROCESS_DATA | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "PROVIDER_PROCESS_DATA"
helpviewer_keywords: 
  - "PROVIDER_PROCESS_DATA 구조"
ms.assetid: ec2362ed-4a0c-4a09-9d66-8ff04e4f41ee
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# PROVIDER_PROCESS_DATA
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 구조는 컴퓨터에서 실행 중인 프로세스에 대 한 정보를 제공 합니다.  
  
## 구문  
  
```cpp#  
typedef struct tagPROVIDER_PROCESS_DATA {  
   PROVIDER_FIELDS    Fields;  
   PROGRAM_NODE_ARRAY ProgramNodes;  
   BOOL               fIsDebuggerPresent;  
} PROVIDER_PROCESS_DATA;  
```  
  
```c#  
public struct PROVIDER_PROCESS_DATA {  
   public uint               Fields;  
   public PROGRAM_NODE_ARRAY ProgramNodes;  
   public int                fIsDebuggerPresent;  
}  
```  
  
## Members  
 필드  
 플래그의 조합에서 [PROVIDER\_FIELDS](../../../extensibility/debugger/reference/provider-fields.md) 입력 필드를 표시 하는 열거입니다.  
  
 ProgramNodes  
 A [PROGRAM\_NODE\_ARRAY](../../../extensibility/debugger/reference/program-node-array.md) 프로그램 노드의 배열을 포함 하는 구조입니다.  
  
 fIsDebuggerPresent  
 0이 아닌 \(`TRUE`\) 경우는 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] 디버거에서 실행, 0 \(`FALSE`\) 되지 않은 경우입니다.  
  
## 설명  
 이 구조체에 전달 되는 [GetProviderProcessData](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md) 메서드는 입력 위치에 있습니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [PROVIDER\_FIELDS](../../../extensibility/debugger/reference/provider-fields.md)   
 [PROGRAM\_NODE\_ARRAY](../../../extensibility/debugger/reference/program-node-array.md)   
 [GetProviderProcessData](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md)