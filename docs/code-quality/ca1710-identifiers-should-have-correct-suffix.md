---
title: ': Ca1710 식별자에는 올바른 접미사 사용 해야 합니다. | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA1710
- IdentifiersShouldHaveCorrectSuffix
helpviewer_keywords:
- IdentifiersShouldHaveCorrectSuffix
- CA1710
ms.assetid: 2b8e6dce-b4e8-4a66-ba9a-6b79be5bfe8c
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ae9af2a4178dd06d9f849adeb1dc42c1c0bffe08
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="ca1710-identifiers-should-have-correct-suffix"></a>CA1710: 식별자에는 올바른 접미사를 사용해야 합니다.
|||  
|-|-|  
|TypeName|IdentifiersShouldHaveCorrectSuffix|  
|CheckId|CA1710|  
|범주|Microsoft.Naming|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 식별자는 올바른 접미사는 없습니다.  
  
## <a name="rule-description"></a>규칙 설명  
 규칙에 따라 특정 기본 형식을 확장 하거나 특정 인터페이스 또는 이러한 형식에서 파생 된 형식을 구현 하는 형식의 이름에는 기본 형식이 나 인터페이스와 연결 된 접미사를 갖습니다.  
  
 명명 규칙은 공통 된 모양을 라이브러리에 대 한 공용 언어 런타임을 대상으로 합니다. 이렇게 하면 새 소프트웨어 라이브러리에 필요 하 고 관리 되는 코드를 개발에 대 한 전문 지식이 있는 사용자가 라이브러리를 개발 하는 신뢰성이 향상를 배워야 할 필요성이 줄어듭니다.  
  
 다음 표에서 기본 형식과 연관 된 접미사가 있는 인터페이스를 나열 합니다.  
  
|기본 형식/인터페이스|접미사|  
|--------------------------|------------|  
|<xref:System.Attribute?displayProperty=fullName>|특성|  
|<xref:System.EventArgs?displayProperty=fullName>|EventArgs|  
|<xref:System.Exception?displayProperty=fullName>|예외|  
|<xref:System.Collections.ICollection?displayProperty=fullName>|컬렉션|  
|<xref:System.Collections.IDictionary?displayProperty=fullName>|사전|  
|<xref:System.Collections.IEnumerable?displayProperty=fullName>|컬렉션|  
|<xref:System.Collections.Queue?displayProperty=fullName>|컬렉션 또는 큐|  
|<xref:System.Collections.Stack?displayProperty=fullName>|컬렉션 또는 스택|  
|<xref:System.Collections.Generic.ICollection%601?displayProperty=fullName>|컬렉션|  
|<xref:System.Collections.Generic.IDictionary%602?displayProperty=fullName>|사전|  
|<xref:System.Data.DataSet?displayProperty=fullName>|데이터 집합|  
|<xref:System.Data.DataTable?displayProperty=fullName>|DataTable 또는 컬렉션|  
|<xref:System.IO.Stream?displayProperty=fullName>|스트림|  
|<xref:System.Security.IPermission?displayProperty=fullName>|사용 권한|  
|<xref:System.Security.Policy.IMembershipCondition?displayProperty=fullName>|조건|  
|이벤트 처리기 대리자입니다.|이벤트 처리기|  
  
 구현 하는 형식은 <xref:System.Collections.ICollection> 사전, 스택 또는 큐 이름을 사용할 수는 형식의 용도 대 한 의미 있는 정보를 제공 하는 같은 일반화 된 형식의 데이터 구조를 가지는 및입니다.  
  
 구현 하는 형식은 <xref:System.Collections.ICollection> 되며 특정 항목의 컬렉션에는 'Collection' 라는 단어로 끝나는 이름이 있어야 합니다. 예를 들어 컬렉션의 <xref:System.Collections.Queue> 개체 이름 'QueueCollection'는 것입니다. 'Collection' 접미사를 사용 하 여 컬렉션의 멤버를 열거 해야 함을 의미는 `foreach` (`For Each` 에 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) 문입니다.  
  
 구현 하는 형식은 <xref:System.Collections.IDictionary> 도 구현 하는 경우에 '사전' 라는 단어로 끝나는 <xref:System.Collections.IEnumerable> 또는 <xref:System.Collections.ICollection>합니다. 'Collection'와 '사전' 접미사 명명 규칙을 사용 하면 다음과 같은 두 개의 열거형 패턴을 구분할 수 있도록 합니다.  
  
 'Collection' 접미사를 사용 하는 형식에는이 열거형 패턴을 따릅니다.  
  
```  
foreach(SomeType x in SomeCollection) { }  
```  
  
 '사전' 접미사를 사용 하는 형식에는이 열거형 패턴을 따릅니다.  
  
```  
foreach(SomeType x in SomeDictionary.Values) { }  
```  
  
 A <xref:System.Data.DataSet> 개체의 컬렉션으로 구성 됩니다 <xref:System.Data.DataTable> 개체의 컬렉션으로 구성 된 <xref:System.Data.DataColumn?displayProperty=fullName> 및 <xref:System.Data.DataRow?displayProperty=fullName> 다른 규칙 으로부터 개체입니다. 이러한 컬렉션은 구현 <xref:System.Collections.ICollection> 기본 통해 <xref:System.Data.InternalDataCollectionBase?displayProperty=fullName> 클래스입니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 형식을 이름을 올바른 용어도 뒤 추가 됩니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 형식이 확장 될 수 있거나 임의의 다양 한 항목 집합을 보유 하는 일반화 된 데이터 구조 이면 'Collection' 접미사를 사용 하려면 경고를 표시 하지 않아도 안전 합니다. 이 경우 구현, 성능 또는 기타 특성의 데이터 구조에 대 한 의미 있는 정보를 제공 하는 이름을 적합할 수 있습니다 (예를 들어 BinaryTree). 특정 형식 (예를 들어 StringCollection)의 컬렉션을 나타내는 위치 하는 경우에 표시 해야이 규칙에서는 경고를에서 접미사 유형을 사용 하 여 열거 해야 함을 나타내기 때문에 `foreach` 문.  
  
 다른 접미사에 대 한이 규칙에서는 경고를에서 표시 하지 마십시오. 접미사를 사용 하면 그 용도를 형식 이름에서 발생할 수 있습니다.  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA1711: 식별자에는 올바른 접미사를 사용해야 합니다.](../code-quality/ca1711-identifiers-should-not-have-incorrect-suffix.md)  
  
## <a name="see-also"></a>참고 항목  
 [특성](/dotnet/standard/design-guidelines/attributes)   
 [이벤트 처리 및 발생](/dotnet/standard/events/index)  