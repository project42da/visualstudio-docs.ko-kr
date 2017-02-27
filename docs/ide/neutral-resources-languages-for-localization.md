---
title: "지역화를 위한 중립 리소스 언어 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "culture, 리소스 찾기"
  - "전역화[Visual Studio], 리소스"
  - "지역화[Visual Studio], 리소스"
  - "중립 리소스"
  - "NeutralResourcesLanguageAttribute 클래스"
  - "리소스[Visual Studio], 대체(fallback) 시스템"
ms.assetid: ef064995-3b84-4698-a708-9689b7723533
caps.latest.revision: 8
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 8
---
# 지역화를 위한 중립 리소스 언어
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

<xref:System.Resources.NeutralResourcesLanguageAttribute> 클래스에서는 주 어셈블리에 포함된 리소스의 culture를 지정합니다.  이 특성은 성능 향상을 위해 사용되므로 <xref:System.Resources.ResourceManager> 개체에서 주 어셈블리에 포함된 리소스를 검색하지 않습니다.  
  
 아래 코드에서는 중립 리소스 언어를 설정하는 방법을 보여 줍니다.  빌드 스크립트나 AssemblyInfo.vb 또는 AssemblyInfo.cs 파일에 이 코드를 넣을 수 있습니다.  
  
```vb#  
' Set neutral resources language for assembly.  
<Assembly: NeutralResourcesLanguageAttribute("en")>  
  
```  
  
```c#  
// Set neutral resources language for assembly.  
[assembly: NeutralResourcesLanguageAttribute("en")]  
```  
  
## 참고 항목  
 <xref:System.Resources.ResourceManager>   
 [.NET Framework 기반의 국가별 응용 프로그램 소개](../ide/introduction-to-international-applications-based-on-the-dotnet-framework.md)   
 [지역화를 위한 리소스의 계층적 구성](../ide/hierarchical-organization-of-resources-for-localization.md)   
 [응용 프로그램 지역화](../ide/localizing-applications.md)   
 [응용 프로그램 전역화 및 지역화](../ide/globalizing-and-localizing-applications.md)