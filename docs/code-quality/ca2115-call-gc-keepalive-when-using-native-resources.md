---
title: "CA2115: GC를 호출 합니다. KeepAlive 네이티브 리소스를 사용 하는 경우 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CallGCKeepAliveWhenUsingNativeResources
- CA2115
helpviewer_keywords:
- CA2115
- CallGCKeepAliveWhenUsingNativeResources
ms.assetid: f00a59a7-2c6a-4bbe-a1b3-7bf77d366f34
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 98833f1feccd70c3bdf140b4d2be7a4ad1a5d6bf
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ca2115-call-gckeepalive-when-using-native-resources"></a>CA2115: 네이티브 리소스를 사용하는 경우에는 GC.KeepAlive를 호출하십시오.
|||  
|-|-|  
|TypeName|CallGCKeepAliveWhenUsingNativeResources|  
|CheckId|CA2115|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 메서드는 종료 자가 있는 형식에 선언 된 참조는 <xref:System.IntPtr?displayProperty=fullName> 또는 <xref:System.UIntPtr?displayProperty=fullName> 필드 되지만 호출 하지 않습니다 <xref:System.GC.KeepAlive%2A?displayProperty=fullName>합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 가비지 컬렉션에에서 있는 경우에 대 한 참조가 더 이상 관리 코드는 개체를 종료 합니다. 개체에 대 한 관리 되지 않는 참조는 가비지 수집이 되지 않더라도 있습니다. 이 규칙에서는 관리되지 않는 리소스가 비관리 코드에서 여전히 사용되고 있는데 종료되려고 할 경우 발생할 수 있는 오류를 감지합니다.  
  
 이 규칙에 있다고 가정 <xref:System.IntPtr> 및 <xref:System.UIntPtr> 필드는 관리 되지 않는 리소스에 대 한 포인터를 저장 합니다. 관리 되지 않는 리소스를 해제 하는 종료자의 목적은 이기 때문에 종료 자가 가리키는 포인터 필드를 통해 관리 되지 않는 리소스를 해제 합니다 규칙 가정 합니다. 이 규칙은 또한 메서드가 관리 되지 않는 리소스가 비관리 코드에 전달할 포인터 필드를 참조 하 고 있다는 가정 합니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면에 대 한 호출을 추가 <xref:System.GC.KeepAlive%2A> 메서드로 현재 인스턴스를 전달 (`this` C# 및 c + +)는 인수입니다. 뒤에 호출 코드의 마지막 줄 가비지 컬렉션에서 개체를 보호 해야 합니다. 에 대 한 호출 직후 <xref:System.GC.KeepAlive%2A>, 개체는 다시 준비가 되었다고 간주 가비지 수집에 참조가 없는 관리 되는 것입니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙은 거짓 긍정을 일으킬 수 있는 몇 가지 사항을 가정 합니다. 이 규칙에서 경고를 표시 하지 않도록 하는 경우 안전 하 게 있습니다.  
  
-   종료자 내용의 압축을 해제 하지 않는 <xref:System.IntPtr> 또는 <xref:System.UIntPtr> 메서드에 의해 참조 되는 필드입니다.  
  
-   메서드를 통과 하지 못하는 <xref:System.IntPtr> 또는 <xref:System.UIntPtr> 필드를 비관리 코드로 합니다.  
  
 제외 하기 전에 다른 메시지를 주의 깊게 검토 합니다. 이 규칙에서는 디버그 하 고 재현 하기 어려운 오류를 감지 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서 `BadMethod`에는 `GC.KeepAlive`에 대한 호출이 포함되지 않으므로 규칙을 위반합니다. `GoodMethod`수정 된 코드를 포함합니다.  
  
> [!NOTE]
>  이 예제는 의사 코드입니다. 코드가 컴파일되고 실행되더라도 관리되지 않는 리소스가 생성 또는 해제되지 않으므로 경고가 발생하지 않습니다.  
  
 [!code-csharp[FxCop.Security.IntptrAndFinalize#1](../code-quality/codesnippet/CSharp/ca2115-call-gc-keepalive-when-using-native-resources_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.GC.KeepAlive%2A?displayProperty=fullName>   
 <xref:System.IntPtr?displayProperty=fullName>   
 <xref:System.Object.Finalize%2A?displayProperty=fullName>   
 <xref:System.UIntPtr?displayProperty=fullName>   
 [삭제 패턴](/dotnet/standard/design-guidelines/dispose-pattern)