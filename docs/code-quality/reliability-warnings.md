---
title: 안정성 경고 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.reliabilityrules
helpviewer_keywords:
- warnings, reliability
- reliability warnings
- managed code analysis warnings, reliability warnings
ms.assetid: 77886846-10a2-4585-968a-7eb60ebe07e8
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 61f7757a3e97f8634c593a8aba52ae1df4fdba73
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="reliability-warnings"></a>안정성 경고
안정성 경고 올바른 메모리 및 스레드 사용과 같은 라이브러리 및 응용 프로그램 안정성을 지원합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
  
|규칙|설명|  
|----------|-----------------|  
|[CA2000: 범위를 벗어나기 전에 개체를 삭제하십시오.](../code-quality/ca2000-dispose-objects-before-losing-scope.md)|개체의 종료자가 실행되지 못하도록 하는 예외 이벤트가 발생할 수 있기 때문에 개체에 대한 모든 참조가 범위를 벗어나기 전에 개체를 명시적으로 삭제해야 합니다.|  
|[CA2001: 문제가 있는 메서드는 호출하지 마십시오.](../code-quality/ca2001-avoid-calling-problematic-methods.md)|멤버에서 잠재적 위험이나 문제가 있는 메서드를 호출합니다.|  
|[CA2002: 약한 ID를 가진 개체를 잠그지 마십시오.](../code-quality/ca2002-do-not-lock-on-objects-with-weak-identity.md)|응용 프로그램 도메인 경계를 가로질러 직접 액세스할 수 있는 개체를 약한 ID를 가진 개체라고 합니다. 약한 ID를 가진 개체에 대해 잠금을 가져오려고 시도하는 스레드는 같은 개체에 대해 잠금을 가진 다른 응용 프로그램 도메인의 스레드에 의해 차단될 수 있습니다.|  
|[CA2003: 파이버를 스레드로 취급하지 마십시오.](../code-quality/ca2003-do-not-treat-fibers-as-threads.md)|관리 되는 스레드 Win32 스레드처럼 취급 됩니다.|  
|[CA2004: GC.KeepAlive에 대한 호출을 제거하십시오.](../code-quality/ca2004-remove-calls-to-gc-keepalive.md)|SafeHandle 사용 하도록 변환 하는 경우 GC에 대 한 모든 호출을 제거 합니다. KeepAlive (개체)입니다. 이 경우 클래스 GC를 호출할 필요가 없습니다. 종료 자가 없는 되지만 운영 체제를 마무리 하려면 SafeHandle에 의존 가정 KeepAlive를 처리 합니다.|  
|[CA2006: SafeHandle을 사용하여 네이티브 리소스를 캡슐화하십시오.](../code-quality/ca2006-use-safehandle-to-encapsulate-native-resources.md)|관리 코드에 IntPtr을 사용하는 것은 잠재적인 보안 및 안정성 문제를 나타냅니다. IntPtr을 사용할 때마다 SafeHandle 또는 유사한 기술을 대신 사용해야 하는지 여부를 결정하도록 검토해야 합니다.|