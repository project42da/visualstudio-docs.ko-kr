---
title: "CA1058: 형식은 특정 기본 형식을 확장하면 안 됩니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "TypesShouldNotExtendCertainBaseTypes"
  - "CA1058"
helpviewer_keywords: 
  - "CA1058"
  - "TypesShouldNotExtendCertainBaseTypes"
ms.assetid: 8446ee40-beb1-49fa-8733-4d8e813471c0
caps.latest.revision: 24
caps.handback.revision: 24
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1058: 형식은 특정 기본 형식을 확장하면 안 됩니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|TypesShouldNotExtendCertainBaseTypes|  
|CheckId|CA1058|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## 원인  
 외부에서 볼 수 있는 형식이 특정 기본 형식을 확장합니다.  현재로서 이 규칙은 다음 형식에서 파생되는 형식을 보고합니다.  
  
-   <xref:System.ApplicationException?displayProperty=fullName>  
  
-   <xref:System.Xml.XmlDocument?displayProperty=fullName>  
  
-   <xref:System.Collections.CollectionBase?displayProperty=fullName>  
  
-   <xref:System.Collections.DictionaryBase?displayProperty=fullName>  
  
-   <xref:System.Collections.Queue?displayProperty=fullName>  
  
-   <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>  
  
-   <xref:System.Collections.SortedList?displayProperty=fullName>  
  
-   <xref:System.Collections.Stack?displayProperty=fullName>  
  
## 규칙 설명  
 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 버전 1의 경우에는 <xref:System.ApplicationException>에서 새 예외를 파생시킬 것을 권장했습니다.  이 권장 사항이 변경되어 새 예외는 <xref:System.Exception?displayProperty=fullName>에서 파생되거나 <xref:System> 네임스페이스에 있는 해당 클래스의 서브클래스 중 하나에서 파생되어야 합니다.  
  
 내부 개체 모델 또는 데이터 소스의 XML 뷰를 만들고자 하는 경우에는 <xref:System.Xml.XmlDocument>의 서브클래스를 만들지 마십시오.  
  
### 제네릭이 아닌 컬렉션  
 가능하면 제네릭 컬렉션을 사용하거나 확장하십시오.  제네릭이 아닌 코드는 이미 제공한 경우가 아니면 코드에서 확장하지 마십시오.  
  
 **올바르지 않은 사용 예제**  
  
```c#  
public class MyCollection : CollectionBase  
{  
}  
  
public class MyReadOnlyCollection : ReadOnlyCollectionBase  
{  
}  
```  
  
 **올바른 사용 예제**  
  
```c#  
public class MyCollection : Collection<T>  
{  
}  
  
public class MyReadOnlyCollection : ReadOnlyCollection<T>  
{  
}  
```  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 형식을 다른 기본 형식이나 제네릭 컬렉션에서 파생시킵니다.  
  
## 경고를 표시하지 않는 경우  
 <xref:System.ApplicationException>과 관련된 위반의 경우 이 규칙에 따른 경고를 표시해야 합니다.  <xref:System.Xml.XmlDocument>에 대한 위반의 경우 이 규칙에서 경고를 표시하지 않도록 설정해도 안전합니다.  코드가 이미 발표된 경우 제네릭이 아닌 컬렉션에 대한 경고를 표시하지 않도록 설정해도 안전합니다.