---
title: "CA1305: IFormatProvider를 지정하십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SpecifyIFormatProvider"
  - "CA1305"
helpviewer_keywords: 
  - "CA1305"
  - "SpecifyIFormatProvider"
ms.assetid: fb34ed9a-4eab-47cc-8eef-3068a4a1397e
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 22
---
# CA1305: IFormatProvider를 지정하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|SpecifyIFormatProvider|  
|CheckId|CA1305|  
|범주|Microsoft.Globalization|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 메서드 또는 생성자가 <xref:System.IFormatProvider?displayProperty=fullName> 매개 변수를 받아들이는 오버로드가 있는 하나 이상의 멤버를 호출하지만 <xref:System.IFormatProvider> 매개 변수를 사용하는 오버로드는 호출하지 않습니다.  이 규칙에서는 <xref:System.IFormatProvider> 매개 변수를 무시한다고 문서화되어 있는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 메서드와 다음의 추가적인 메서드에 대한 호출을 무시합니다.  
  
-   <xref:System.Activator.CreateInstance%2A?displayProperty=fullName>  
  
-   <xref:System.Resources.ResourceManager.GetObject%2A?displayProperty=fullName>  
  
-   <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=fullName>  
  
## 규칙 설명  
 <xref:System.Globalization.CultureInfo?displayProperty=fullName> 또는 <xref:System.IFormatProvider> 개체가 제공되지 않으면 오버로드된 멤버에서 제공하는 기본값이 모든 로캘에서 원하는 효과를 나타내지 않을 수 있습니다.  또한 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 멤버에서는 코드에 적합하지 않을 수 있다는 가정 하에 기본 문화권 및 서식을 선택합니다.  현재 시나리오에 맞게 코드가 작동하도록 하려면 다음 지침에 따라 문화권별 정보를 제공해야 합니다.  
  
-   값이 사용자에게 표시될 경우 현재 문화권을 사용합니다.  <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName>를 참조하십시오.  
  
-   값이 소프트웨어에서 저장되고 액세스되면, 즉 파일이나 데이터베이스에 유지되면 고정 문화권을 사용합니다.  <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>를 참조하십시오.  
  
-   값의 대상을 모르면 데이터 소비자 또는 공급자가 문화권을 지정하도록 합니다.  
  
 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>는 <xref:System.Resources.ResourceManager?displayProperty=fullName> 클래스의 인스턴스를 사용하여 지역화된 리소스를 검색할 때만 사용됩니다.  
  
 오버로드된 멤버의 기본 동작이 현재 작업에 적합하더라도 문화권별 오버로드를 명시적으로 호출하여 코드가 자체적으로 문서화되고 더욱 쉽게 유지 관리되도록 하는 것이 더 좋습니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 <xref:System.Globalization.CultureInfo> 또는 <xref:System.IFormatProvider>를 사용하는 오버로드를 사용하고 앞에서 설명한 지침에 따라 인수를 지정합니다.  
  
## 경고를 표시하지 않는 경우  
 기본 문화권\/서식 공급자가 올바른 것이 확실하고 코드 유지 관리성이 개발에서 별로 중요하지 않은 경우에는 이 규칙에서 경고를 표시하지 않아도 안전합니다.  
  
## 예제  
 다음 예제에서 `BadMethod`는 이 규칙을 두 번 위반합니다.  `GoodMethod`는 고정 문화권을 <xref:System.String.Compare%2A>로 전달하여 첫 번째 위반 문제를 해결하고, `string3`이 사용자에게 표시되므로 현재 문화권을 <xref:System.String.ToLower%2A>로 전달하여 두 번째 위반 문제를 해결합니다.  
  
 [!code-cs[FxCop.Globalization.CultureInfo#1](../code-quality/codesnippet/CSharp/ca1305-specify-iformatprovider_1.cs)]  
  
## 예제  
 다음 예제에서는 <xref:System.DateTime> 형식에서 선택한 기본 <xref:System.IFormatProvider>에 대한 현재 문화권의 효과를 보여 줍니다.  
  
 [!code-cs[FxCop.Globalization.IFormatProvider#1](../code-quality/codesnippet/CSharp/ca1305-specify-iformatprovider_2.cs)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
  **6\/4\/1900 12:15:12 PM**  
**06\/04\/1900 12:15:12**   
## 관련 규칙  
 [CA1304: CultureInfo를 지정하십시오.](../Topic/CA1304:%20Specify%20CultureInfo.md)  
  
## 참고 항목  
 [NIB: Using the CultureInfo Class](http://msdn.microsoft.com/ko-kr/d4329e34-64c3-4d1e-8c73-5b0ee626ba7a)