---
title: AsyncTaskMethodBuilder 구조-내부 멤버 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debug engines, AsyncTaskMethodBuilder structure [.NET Framework]
- AsyncTaskMethodBuilder structure [.NET Framework debug engines]
ms.assetid: f32f5857-7ef8-45fd-8b5a-7f644eb98b11
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ecb114c1c05a4e31d58746948cec76317012328e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="asynctaskmethodbuilder-structure---internal-members"></a>AsyncTaskMethodBuilder 구조-내부 멤버
이 항목의 내부 멤버를 설명 합니다.는 <xref:System.Runtime.CompilerServices.AsyncTaskMethodBuilder> 클래스입니다. 이 클래스에 대 한 일반 정보에 대 한 참조는 <xref:System.Runtime.CompilerServices.AsyncTaskMethodBuilder> 참조 항목입니다.  
  
 **Namespace:** <xref:System.Runtime.CompilerServices?displayProperty=fullName>  
  
 **어셈블리:** (mscorlib.dll)에 mscorlib  
  
 .NET Framework에서 이러한 내부 멤버에 액세스할 수 없으므로, 다음 구문은 공통 중간 언어 (CIL) 제공 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
.class public sequential ansi sealed beforefieldinit System.Runtime.CompilerServices.AsyncTaskMethodBuilder  
       extends System.ValueType  
       implements System.Runtime.CompilerServices.IAsyncMethodBuilder  
```  
  
## <a name="internal-members"></a>내부 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[ObjectIdForDebugger 속성](../../extensibility/debugger/asynctaskmethodbuilder-objectidfordebugger-property.md)|고유 하 게 식별 하 고 디버거가이 작성기를 사용할 수 있는 개체를 가져옵니다.|  
|[m_builder 필드](../../extensibility/debugger/asynctaskmethodbuilder-m-builder-field.md)|이 제네릭이 아닌 인스턴스 위임 하는 일반 작성기 개체를 나타냅니다.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Runtime.CompilerServices.AsyncTaskMethodBuilder>   
 [.NET Framework에 대한 병렬 확장 기능 내부](../../extensibility/debugger/parallel-extension-internals-for-the-dotnet-framework.md)