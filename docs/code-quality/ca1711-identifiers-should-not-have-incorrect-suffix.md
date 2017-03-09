---
title: "CA1711: 식별자에는 올바른 접미사를 사용해야 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA1711"
  - "IdentifiersShouldNotHaveIncorrectSuffix"
helpviewer_keywords: 
  - "CA1711"
  - "IdentifiersShouldNotHaveIncorrectSuffix"
ms.assetid: a63359ab-386d-44ae-b381-ee3a983aca29
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1711: 식별자에는 올바른 접미사를 사용해야 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|IdentifiersShouldNotHaveIncorrectSuffix|  
|CheckId|CA1711|  
|범주|Microsoft.Naming|  
|변경 수준|주요 변경|  
  
## 원인  
 식별자에 잘못된 접미사가 있습니다.  
  
## 규칙 설명  
 규칙에 따라 특정 기본 형식을 확장하거나 특정 인터페이스를 구현하는 형식의 이름 또는 이러한 형식에서 파생되는 형식의 이름만이 예약된 특정 접미사로 끝나야 합니다.  다른 형식 이름에는 이러한 예약된 접미사를 사용하면 안 됩니다.  
  
 다음 표에서는 예약된 접미사 및 이와 관련된 기본 형식과 인터페이스를 나열합니다.  
  
|접미사|기본 형식\/인터페이스|  
|---------|------------------|  
|특성|<xref:System.Attribute?displayProperty=fullName>|  
|Collection|<xref:System.Collections.ICollection?displayProperty=fullName><br /><br /> <xref:System.Collections.IEnumerable?displayProperty=fullName><br /><br /> <xref:System.Collections.Queue?displayProperty=fullName><br /><br /> <xref:System.Collections.Stack?displayProperty=fullName><br /><br /> <xref:System.Collections.Generic.ICollection%601?displayProperty=fullName><br /><br /> <xref:System.Data.DataSet?displayProperty=fullName><br /><br /> <xref:System.Data.DataTable?displayProperty=fullName>|  
|Dictionary의 비교|<xref:System.Collections.IDictionary?displayProperty=fullName><br /><br /> <xref:System.Collections.Generic.IDictionary%602?displayProperty=fullName>|  
|EventArgs|<xref:System.EventArgs?displayProperty=fullName>|  
|EventHandler|이벤트 처리기 대리자입니다.|  
|예외|<xref:System.Exception?displayProperty=fullName>|  
|권한|<xref:System.Security.IPermission?displayProperty=fullName>|  
|Queue|<xref:System.Collections.Queue?displayProperty=fullName>|  
|스택|<xref:System.Collections.Stack?displayProperty=fullName>|  
|스트림|<xref:System.IO.Stream?displayProperty=fullName>|  
  
 또한 다음 접미사는 사용하면 **안 됩니다**.  
  
-   대리자  
  
-   Enum  
  
-   Impl \- 이 접미사 대신 'Core' 사용  
  
-   이전 버전의 같은 형식과 구별하기 위한 Ex 또는 유사 접미사  
  
 명명 규칙은 공용 언어 런타임을 대상으로 하는 라이브러리에 공통적인 모양을 적용합니다.  이 라이브러리는 관리 코드 개발에 대한 전문 지식을 가진 사람에 의해 개발되었으므로 새 소프트웨어 라이브러리에 익숙해지는 데 필요한 학습 기간을 단축하고 고객의 신뢰를 높여 줍니다.  
  
## 위반 문제를 해결하는 방법  
 형식 이름에서 해당 접미사를 제거합니다.  
  
## 경고를 표시하지 않는 경우  
 응용 프로그램 도메인에서 접미사에 명확한 의미가 있지 않으면 이 규칙에서 경고를 표시 하지 마십시오.  
  
## 관련 규칙  
 [CA1710: 식별자에는 올바른 접미사를 사용해야 합니다.](../Topic/CA1710:%20Identifiers%20should%20have%20correct%20suffix.md)  
  
## 참고 항목  
 [특성](../Topic/Attributes1.md)   
 [이벤트 및 대리자](http://msdn.microsoft.com/ko-kr/d98fd58b-fa4f-4598-8378-addf4355a115)