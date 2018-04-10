---
title: .NET Framework에 대 한 확장 내부 병렬 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- debug engines, internals [.NET Framework]
ms.assetid: 93e07cfa-91fa-464c-b866-8bf5570411df
caps.latest.revision: 11
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 4cc64270cabb3e30ee3c13a1617222349e7b3677
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/10/2018
---
# <a name="parallel-extension-internals-for-the-net-framework"></a>.NET Framework에 대 한 병렬 확장 내부 기능
이 섹션에서는 내부 형식, 메서드, 설명 및.NET Framework의 병렬 확장에 대 한 사용자 지정 디버거를 구현 하는 데 도움이 되는 클래스의 필드입니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [작업 클래스](../../extensibility/debugger/task-class-internal-members.md)  
 내부 데이터 멤버를 설명는 <xref:System.Threading.Tasks.Task?displayProperty=fullName> 클래스입니다.  
  
 [TaskScheduler 클래스](../../extensibility/debugger/taskscheduler-class-internal-members.md)  
 내부 데이터 멤버를 설명는 <xref:System.Threading.Tasks.TaskScheduler?displayProperty=fullName> 클래스입니다.  
  
 [ContingentProperties 클래스](../../extensibility/debugger/contingentproperties-class-internal-members.md)  
 내부 데이터 멤버를 설명는 `System.Threading.Tasks.ContingentProperties` 클래스입니다.  
  
 [AsyncTaskMethodBuilder 구조](../../extensibility/debugger/asynctaskmethodbuilder-structure-internal-members.md)  
 내부 멤버를 설명는 <xref:System.Runtime.CompilerServices.AsyncTaskMethodBuilder> 구조입니다.  
  
 [AsyncTaskMethodBuilder\<TResult > 구조](../../extensibility/debugger/asynctaskmethodbuilder-tresult-structure-internal-members.md)  
 내부 멤버를 설명는 <xref:System.Runtime.CompilerServices.AsyncTaskMethodBuilder%601> 구조입니다.  
  
 [AsyncVoidMethodBuilder 구조](../../extensibility/debugger/asyncvoidmethodbuilder-structure-internal-members.md)  
 내부 멤버를 설명는 <xref:System.Runtime.CompilerServices.AsyncVoidMethodBuilder> 구조입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Threading.Tasks.Task?displayProperty=fullName>   
 <xref:System.Threading.Tasks.TaskScheduler?displayProperty=fullName>   
 [Visual Studio 디버거 확장성](../../extensibility/debugger/visual-studio-debugger-extensibility.md)   
 [병렬 프로그래밍](/dotnet/standard/parallel-programming/index)