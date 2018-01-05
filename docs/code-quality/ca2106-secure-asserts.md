---
title: "CA2106: 어설션을 안전 어설션 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2106
- SecureAsserts
helpviewer_keywords:
- CA2106
- SecureAsserts
ms.assetid: 91feb36e-6e2c-436c-8272-5aee31f77e98
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 33e200b06ed9bb0999116ea91a64b06aaa879067
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ca2106-secure-asserts"></a>CA2106: 어설션을 안전하게 하십시오.
|||  
|-|-|  
|TypeName|SecureAsserts|  
|CheckId|CA2106|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 메서드에서 권한을 어설션하는데 호출자에 대해 보안 검사가 수행되지 않습니다.  
  
## <a name="rule-description"></a>규칙 설명  
 보안 검사를 수행하지 않고 보안 권한을 어설션하면 코드에 보안상 취약한 부분이 남아 있을 수 있습니다. 보안 권한이 어설션 되 면 보안 스택 워크를 중지 합니다. 호출자에 대 한 검사를 수행 하지 않고 사용 권한을 어설션하 면 호출자에 게 직접 코드를 실행할 수 없습니다 사용자 권한을 사용 하 여 합니다. 보안 검사는 허용 가능한만 확신할 때 assert 유해한 방식으로 사용할 수 없는 어설션 합니다. Assert는 호출 코드가 무해 이면 치명적이 지 또는 사용자가 호출 하는 코드에 임의의 정보를 전달할 수 없습니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 메서드 또는 해당 선언 형식에는 보안 요청을 추가 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 신중 하 게 보안을 검토 한 후에이 규칙에서 경고를 표시 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Security.CodeAccessPermission.Assert%2A?displayProperty=fullName>   
 [보안 코딩 지침](/dotnet/standard/security/secure-coding-guidelines)