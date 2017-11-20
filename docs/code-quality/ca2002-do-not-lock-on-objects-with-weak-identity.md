---
title: "CA2002: 약한 id 가진 개체를 잠그지 마십시오 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DoNotLockOnObjectsWithWeakIdentity
- CA2002
helpviewer_keywords:
- CA2002
- DoNotLockOnObjectsWithWeakIdentity
ms.assetid: 16100b39-c6fc-452b-8fca-8b459a26c286
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 54a7693f5e2921b7cab60278c870c456084c56f2
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ca2002-do-not-lock-on-objects-with-weak-identity"></a>CA2002: 약한 ID를 가진 개체를 잠그지 마십시오.
|||  
|-|-|  
|TypeName|DoNotLockOnObjectsWithWeakIdentity|  
|CheckId|CA2002|  
|범주|Microsoft.Reliability|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 스레드를 약한 id를 가진 개체에 대 한 잠금을 획득 하려고 시도 합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 응용 프로그램 도메인 경계를 가로질러 직접 액세스할 수 있는 개체를 약한 ID를 가진 개체라고 합니다. 약한 ID를 가진 개체에 대해 잠금을 가져오려고 시도하는 스레드는 같은 개체에 대해 잠금을 가진 다른 응용 프로그램 도메인의 스레드에 의해 차단될 수 있습니다. 형식은 약한 id를가지고 있으며 규칙에서 플래그가 지정:  
  
-   <xref:System.MarshalByRefObject>  
  
-   <xref:System.ExecutionEngineException>  
  
-   <xref:System.OutOfMemoryException>  
  
-   <xref:System.StackOverflowException>  
  
-   <xref:System.String>  
  
-   <xref:System.Reflection.MemberInfo>  
  
-   <xref:System.Reflection.ParameterInfo>  
  
-   <xref:System.Threading.Thread>  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 설명 섹션의 목록에 포함 되지 않은 형식에서 개체를 사용 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA2213: 삭제 가능한 필드는 삭제해야 합니다.](../code-quality/ca2213-disposable-fields-should-be-disposed.md)  
  
## <a name="example"></a>예제  
 다음 예제에서는 규칙을 위반 하는 몇 개의 개체 잠금을 보여 줍니다.  
  
 [!code-vb[FxCop.Reliability.LockWeakObjects#1](../code-quality/codesnippet/VisualBasic/ca2002-do-not-lock-on-objects-with-weak-identity_1.vb)]
 [!code-csharp[FxCop.Reliability.LockWeakObjects#1](../code-quality/codesnippet/CSharp/ca2002-do-not-lock-on-objects-with-weak-identity_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Threading.Monitor>   
 <xref:System.AppDomain>   
 [lock 문](/dotnet/csharp/language-reference/keywords/lock-statement)   
 [SyncLock 문](/dotnet/visual-basic/language-reference/statements/synclock-statement)