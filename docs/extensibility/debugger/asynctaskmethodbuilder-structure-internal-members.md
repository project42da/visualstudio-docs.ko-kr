---
title: "AsyncTaskMethodBuilder 구조-내부 멤버 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "디버그 엔진, AsyncTaskMethodBuilder 구조체 [.NET Framework]"
  - "AsyncTaskMethodBuilder 구조체 [.NET Framework 디버그 엔진]"
ms.assetid: f32f5857-7ef8-45fd-8b5a-7f644eb98b11
caps.latest.revision: 5
caps.handback.revision: 5
ms.author: "gregvanl"
manager: "ghogen"
---
# AsyncTaskMethodBuilder 구조-내부 멤버
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

이 항목의 내부 멤버를 설명 합니다.는 <xref:System.Runtime.CompilerServices.AsyncTaskMethodBuilder> 클래스입니다. 이 클래스에 대 한 일반 정보에 대 한 참조는 <xref:System.Runtime.CompilerServices.AsyncTaskMethodBuilder> 참조 항목입니다.  
  
 **네임 스페이스:** <xref:System.Runtime.CompilerServices?displayProperty=fullName>  
  
 **어셈블리:** \(mscorlib.dll\)에 mscorlib  
  
 .NET Framework에서 이러한 내부 멤버를 액세스할 수 없으므로, 다음 구문은 공통 중간 언어 \(CIL\) 제공 됩니다.  
  
## 구문  
  
```  
.class public sequential ansi sealed beforefieldinit System.Runtime.CompilerServices.AsyncTaskMethodBuilder  
       extends System.ValueType  
       implements System.Runtime.CompilerServices.IAsyncMethodBuilder  
```  
  
## 내부 멤버  
  
|이름|설명|  
|--------|--------|  
|[ObjectIdForDebugger 속성](../../extensibility/debugger/asynctaskmethodbuilder-objectidfordebugger-property.md)|디버거에이 작성기를 고유 하 게 식별 하는 데 사용할 수 있는 개체를 가져옵니다.|  
|[m\_builder 필드](../../extensibility/debugger/asynctaskmethodbuilder-m-builder-field.md)|이 제네릭이 아닌 인스턴스 위임 하는 일반 작성기 개체를 나타냅니다.|  
  
## 참고 항목  
 <xref:System.Runtime.CompilerServices.AsyncTaskMethodBuilder>   
 [.NET Framework에 대 한 병렬 확장 기능의 내부](../../extensibility/debugger/parallel-extension-internals-for-the-dotnet-framework.md)