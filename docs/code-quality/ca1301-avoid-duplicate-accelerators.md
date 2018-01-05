---
title: ": Ca1301 중복 액셀러레이터 키 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1301
- AvoidDuplicateAccelerators
helpviewer_keywords:
- CA1301
- AvoidDuplicateAccelerators
ms.assetid: 20570a00-864b-459c-a1fa-a6e9db5f1001
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: a61e4c0ab9957772609c20623f0bc6ef7659a9d2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1301-avoid-duplicate-accelerators"></a>CA1301: 중복 액셀러레이터 키를 사용하지 마십시오.
|||  
|-|-|  
|TypeName|AvoidDuplicateAccelerators|  
|CheckId|CA1301|  
|범주|Microsoft.Globalization|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 형식 확장 <xref:System.Windows.Forms.Control?displayProperty=fullName> 리소스 파일에 저장 된 동일한 액세스 키가 있는 두 개 이상의 최상위 컨트롤을 포함 합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 액셀러레이터 키라고도 하는 선택키를 사용하면 Alt 키를 사용하여 키보드로 컨트롤에 액세스할 수 있습니다. 여러 컨트롤에 중복되는 선택키가 있으면 선택키의 동작이 제대로 정의되지 않은 경우입니다. 사용자 선택 키를 사용 하 여 원하는 컨트롤에 액세스할 수 수 있으며 되는 것과 다른 제어를 받아들일 수 있습니다.  
  
 이 규칙의 현재 구현에서 메뉴 항목을 무시합니다. 그러나 동일한 하위 메뉴에 메뉴 항목에는 선택 키와 동일한 없어야 합니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 모든 컨트롤에 대 한 고유 액세스 키를 정의 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 동일한 액세스 키가 있는 두 컨트롤을 포함 하는 최소한의 형태를 보여 줍니다. 키가 표시 되지 않는; 리소스 파일에 저장 그러나 해당 값 표시는 주석 처리 된 아웃 `checkBox.Text` 선입니다. 중복 액셀러레이터 키의 동작을 교환 하 여 검사할 수 있습니다는 `checkBox.Text` 줄 주석 처리 합니다. 그러나이 경우이 예제에서는 생성 하지 않습니다는 경고 규칙에서.  
  
 [!code-csharp[FxCop.Globalization.AvoidDuplicateAccels#1](../code-quality/codesnippet/CSharp/ca1301-avoid-duplicate-accelerators_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Resources.ResourceManager?displayProperty=fullName>   
 [데스크톱 앱의 리소스](/dotnet/framework/resources/index)