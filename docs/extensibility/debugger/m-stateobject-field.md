---
title: "m_stateObject 필드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "m_stateObject 필드, 작업 클래스 [.NET Framework 디버그 엔진]"
ms.assetid: 68c54b22-3e1c-4031-b9c7-b972c519d8a0
caps.latest.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 13
---
# m_stateObject 필드
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

작업에서 사용할 데이터를 나타내는 개체입니다.  
  
 **네임 스페이스:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **어셈블리:** \(mscorlib.dll\)에 mscorlib  
  
 .NET Framework에서이 내부 멤버를 액세스할 수 없으므로, 다음 구문은 공통 중간 언어 \(CIL\) 제공 됩니다.  
  
## 구문  
  
```  
.field assembly object m_stateObject  
```  
  
## 설명  
 이 `state` 매개 변수는 <xref:System.Threading.Tasks.Task.%23ctor%2A> 생성자입니다. 에 대 한 지원 필드 이기도 <xref:System.Threading.Tasks.Task.AsyncState%2A?displayProperty=fullName> 속성입니다.  
  
## 참고 항목  
 [작업 클래스](../../extensibility/debugger/task-class-internal-members.md)