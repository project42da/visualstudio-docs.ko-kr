---
title: 'CA1058: 형식은 특정 기본 형식을 확장 하지 해야 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- TypesShouldNotExtendCertainBaseTypes
- CA1058
helpviewer_keywords:
- CA1058
- TypesShouldNotExtendCertainBaseTypes
ms.assetid: 8446ee40-beb1-49fa-8733-4d8e813471c0
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 70d7ec2767542db8e38d60198b5f00554897e4ae
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="ca1058-types-should-not-extend-certain-base-types"></a>CA1058: 형식은 특정 기본 형식을 확장하면 안 됩니다.
|||  
|-|-|  
|TypeName|TypesShouldNotExtendCertainBaseTypes|  
|CheckId|CA1058|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 외부에서 볼 수 있는 형식이 특정 기본 형식을 확장합니다. 현재,이 규칙은 보고 형식에서 파생 되는 형식:  
  
-   <xref:System.ApplicationException?displayProperty=fullName>  
  
-   <xref:System.Xml.XmlDocument?displayProperty=fullName>  
  
-   <xref:System.Collections.CollectionBase?displayProperty=fullName>  
  
-   <xref:System.Collections.DictionaryBase?displayProperty=fullName>  
  
-   <xref:System.Collections.Queue?displayProperty=fullName>  
  
-   <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>  
  
-   <xref:System.Collections.SortedList?displayProperty=fullName>  
  
-   <xref:System.Collections.Stack?displayProperty=fullName>  
  
## <a name="rule-description"></a>규칙 설명  
 에 대 한 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 버전 1에서 새 예외를 파생 시키는 권장 되었던 것 <xref:System.ApplicationException>합니다. 권장 구성이 변경 되 고 새 예외에서 파생 되어야 <xref:System.Exception?displayProperty=fullName> 또는 해당 서브 클래스에서 중 하나는 <xref:System> 네임 스페이스입니다.  
  
 서브 클래스를 만들지 마십시오 <xref:System.Xml.XmlDocument> 기본 개체 모델 또는 데이터 원본에 대 한 XML 뷰를 만들려는 경우.  
  
### <a name="non-generic-collections"></a>제네릭이 아닌 컬렉션  
 사용 하거나 가능 하면 제네릭 컬렉션을 확장 합니다. 이전에 제공한 경우가 아니면 사용자 코드에서 제네릭이 아닌 컬렉션을 확장 하지 않습니다.  
  
 **잘못 된 사용 예제를 보려면**  
  
```csharp  
public class MyCollection : CollectionBase  
{  
}  
  
public class MyReadOnlyCollection : ReadOnlyCollectionBase  
{  
}  
```  
  
 **올바른 사용 예제**  
  
```csharp  
public class MyCollection : Collection<T>  
{  
}  
  
public class MyReadOnlyCollection : ReadOnlyCollection<T>  
{  
}  
```  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 형식을 서로 다른 기본 형식 또는 제네릭 컬렉션에서 파생 됩니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 에 대 한 위반에 대 한이 규칙에서는 경고를에서 표시 해야 <xref:System.ApplicationException>합니다. 에 대 한 위반에 대 한이 규칙에서는 경고를에서 억제를 안전 하 게 <xref:System.Xml.XmlDocument>합니다. 코드는 이전에 출시 된 경우에 제네릭이 아닌 컬렉션에 대 한 경고를 표시 하지 않으려면 안전 합니다.