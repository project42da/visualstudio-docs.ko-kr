---
title: "CA2001: 문제가 있는 메서드를 호출 하지 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2001
- AvoidCallingProblematicMethods
helpviewer_keywords:
- CA2001
- AvoidCallingProblematicMethods
ms.assetid: 19db8edb-31ce-441c-b0de-a0f2746155b7
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: da5da213d400f846f634a98dbdbe919cedf03bcd
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ca2001-avoid-calling-problematic-methods"></a>CA2001: 문제가 있는 메서드는 호출하지 마십시오.
|||  
|-|-|  
|TypeName|AvoidCallingProblematicMethods|  
|CheckId|CA2001|  
|범주|Microsoft.Reliability|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 멤버에서 잠재적 위험이나 문제가 있는 메서드를 호출합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 불필요 한 잠재적으로 위험한 메서드 호출을 수행 하지 마십시오.  
  
 이 규칙 위반 멤버 다음 방법 중 하나를 호출할 때 발생 합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|<xref:System.GC.Collect%2A?displayProperty=fullName>|GC를 호출 합니다. Collect를 호출 응용 프로그램의 성능을 크게 저하 될 수 있으며 거의 필요 하지 않습니다. 자세한 내용은 참조는 [푸에르토리코 Mariani 성능 정보](http://go.microsoft.com/fwlink/?LinkId=169256) MSDN에서 블로그 항목입니다.|  
|<xref:System.Threading.Thread.Resume%2A?displayProperty=fullName><br /><br /> <xref:System.Threading.Thread.Suspend%2A?displayProperty=fullName>|Thread.Suspend 및 Thread.Resume 사용이 중단 된 예기치 않은 동작에 있습니다.  다른 클래스를 사용 하 여는 <xref:System.Threading> 네임 스페이스와 같은 <xref:System.Threading.Monitor>, <xref:System.Threading.Mutex>, <xref:System.Threading.Mutex>, 및 <xref:System.Threading.Semaphore> 스레드를 동기화 하거나 리소스를 보호 합니다.|  
|<xref:System.Runtime.InteropServices.SafeHandle.DangerousGetHandle%2A?displayProperty=fullName>|DangerousGetHandle 메서드 유효 하지 않은 핸들을 반환할 수 있으므로 보안 위험이 발생 합니다. 참조는 <xref:System.Runtime.InteropServices.SafeHandle.DangerousAddRef%2A> 및 <xref:System.Runtime.InteropServices.SafeHandle.DangerousRelease%2A> DangerousGetHandle 메서드를 안전 하 게 사용 하는 방법에 대 한 자세한 내용은 메서드.|  
|<xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName><br /><br /> <xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=fullName><br /><br /> <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=fullName>|이러한 메서드는 예기치 않은 위치에서 어셈블리를 로드할 수 있습니다. 예를 들어 Suzanne Cook.NET CLR 정보 블로그 게시물을 참조 [LoadFile vs. LoadFrom](http://go.microsoft.com/fwlink/?LinkId=164450) 및 [바인딩 컨텍스트를 선택](http://go.microsoft.com/fwlink/?LinkId=164451) 어셈블리를 로드 하는 방법에 대 한 정보는 MSDN 웹 사이트에 있습니다.|  
|[CoSetProxyBlanket](http://go.microsoft.com/fwlink/?LinkID=169250) (Ole32)<br /><br /> [CoInitializeSecurity](http://go.microsoft.com/fwlink/?LinkId=169255) (Ole32)|사용자 코드에서 시작 하는 관리 되는 프로세스에서 실행 하는 시점에 너무 늦었습니다를 안정적으로 CoSetProxyBlanket 호출 합니다. 공용 언어 런타임 (CLR) 사용자가 P/Invoke 다음에 나오는 하지 못하게 할 수 있는 초기화 작업을 수행 합니다.<br /><br /> 관리 되는 응용 프로그램에 대 한 CoSetProxyBlanket 호출 필요가 경우 네이티브 코드 (c + +) 실행 파일을 사용 하 여 프로세스를 시작, 네이티브 코드에 CoSetProxyBlanket 호출 하는 다음 프로세스에서 관리 코드 응용 프로그램을 시작 하는 것이 좋습니다. (해야 런타임 버전 번호를 지정 합니다.)|  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 제거 하거나 대체 위험이 나 문제가 있는 메서드를 호출 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 문제가 있는 메서드에 대 한 대안이 사용할 수 있는 경우에이 규칙에서 메시지를 표시 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [안정성 경고](../code-quality/reliability-warnings.md)