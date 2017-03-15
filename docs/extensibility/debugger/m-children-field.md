---
title: "m_children 필드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "m_children 필드 ContingentProperties 클래스 [.NET Framework 디버그 엔진]"
ms.assetid: 0a3b5653-7bc0-4a7a-8963-9020bc52b9cb
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# m_children 필드
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

이 작업에 등록 된 자식 작업의 목록입니다.  
  
 **네임 스페이스:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **어셈블리:** \(mscorlib.dll\)에 mscorlib  
  
 .NET Framework에서이 내부 멤버를 액세스할 수 없으므로, 다음 구문은 공통 중간 언어 \(CIL\) 제공 됩니다.  
  
## 구문  
  
```  
.field public class System.Collections.Generic.List`1<class System.Threading.Tasks.Task> m_children  
```  
  
## 설명  
 작업이 실행 되는 동안 작업을 실행 하는 스레드가이 배열을 액세스 해야 합니다.  
  
 작업이 완료 되는 경우에 다른 스레드에서으로에 아무 것도 추가 하거나 아무 것도를 제거 하지 마십시오이 필드에 액세스할 수 있습니다.  
  
## 참고 항목  
 [ContingentProperties 클래스](../../extensibility/debugger/contingentproperties-class-internal-members.md)