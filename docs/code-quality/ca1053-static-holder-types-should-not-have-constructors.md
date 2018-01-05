---
title: "CA1053: 정적 소유자 형식은 없어야 생성자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- StaticHolderTypesShouldNotHaveConstructors
- CA1053
helpviewer_keywords:
- CA1053
- StaticHolderTypesShouldNotHaveConstructors
ms.assetid: 10302b9a-fa5e-4935-a06a-513d9600f613
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: d482c715e3f93df5fb26f0c88c6b0665b3dee506
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1053-static-holder-types-should-not-have-constructors"></a>CA1053: 정적 소유자 형식에는 생성자를 사용하면 안 됩니다.
|||  
|-|-|  
|TypeName|StaticHolderTypesShouldNotHaveConstructors|  
|CheckId|CA1053|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 public 또는 중첩된 public 형식에서 정적 멤버만 선언하며 public 또는 protected 기본 생성자를 사용합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 호출하는 정적 멤버에 형식의 인스턴스가 필요하지 않기 때문에 생성자가 필요 없습니다. 또한 형식 비정적 멤버가 없기 때문에 인스턴스를 만드는 액세스할 수 없습니다 형식의 멤버에 있습니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 기본 생성자를 제거 하거나 비공개로 설정 합니다.  
  
> [!NOTE]
>  일부 컴파일러는 형식 생성자를 정의 하지 않는 공용 기본 생성자를 자동으로 만듭니다. 경우와 같이 형식 이면 위반을 제거 하기 위해 개인 기본 생성자를 추가 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다. 생성자가 있다는 유형이 정적 형식 인지를 제안 합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는이 규칙을 위반 하는 형식을 보여 줍니다. 소스 코드에서 기본 생성자가 없습니다 것을 볼 수 있습니다. 이 코드를 어셈블리로 컴파일하면 C# 컴파일러는이 규칙에 위반 되는 기본 생성자를 삽입 합니다. 이 문제를 해결 하려면 private 생성자를 선언 합니다.  
  
 [!code-csharp[FxCop.Design.StaticTypes#1](../code-quality/codesnippet/CSharp/ca1053-static-holder-types-should-not-have-constructors_1.cs)]