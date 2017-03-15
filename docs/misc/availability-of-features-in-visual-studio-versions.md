---
title: "Visual Studio 버전에서 사용 가능한 기능 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Visual Studio, 기능 가용성"
ms.assetid: cb2728da-7705-4dea-a1c3-12a0388cb652
caps.latest.revision: 18
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Visual Studio 버전에서 사용 가능한 기능
다음 테이블에서는 나열된 Visual Studio Professional 버전에서 특정 기능이 지원되는지 여부를 보여 줍니다.  
  
-   "예"는 해당 기능이 Visual Studio 버전에 있음을 의미합니다.  
  
-   "추가"는 해당 기능이 Visual Studio 버전에는 없지만 링크를 클릭하여 다운로드하고 자세한 내용을 확인할 수 있음을 의미합니다.  
  
-   "아니요"는 해당 기능이 Visual Studio 버전에 없음을 의미합니다.  
  
||Visual Studio 2010<br /><br /> 및<br /><br /> Visual Studio 2010 SP1|[!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)]|[!INCLUDE[vs_dev12](../data-tools/includes/vs_dev12_md.md)]|  
|-|---------------------------------------------------------|-------------------------------------------------------------------|--------------------------------------------------------------|  
|지원되는 .NET Framework 버전|2.0, 3.0, 3.5 SP1, 4|2.0, 3.0, 3.5 SP1, 4, 4.5|2.0, 3.0, 3.5 SP1, 4, 4.5, 4.5.1|  
|로컬 웹 서버|예|예|예|  
|SQL Server Express|2008|2008|2008|  
|서버 탐색기를 통해 SQL Server 버전에 연결|2000, 2005, 2008|2000, 2005, 2008|2000, 2005, 2008|  
|ASP.NET AJAX <sup>1</sup>|예|예|예|  
|ASP.NET 모델 뷰 컨트롤러|예|예|예|  
|ASP.NET Dynamic Data|예|예|예|  
|MSBuild|예|예|예|  
|ADO.NET Entity Framework|예|예|예|  
|ADO.NET 데이터 서비스|예|예|예|  
|Microsoft Azure 도구|Add|Add||  
|스마트 장치|아니요|아니요||  
|병렬 컴퓨팅|예 <sup>2</sup>|예|예|  
|Windows Communication Foundation|예|예|예|  
|Windows Presentation Foundation|예|예|예|  
|.NET 리치 인터넷 응용 프로그램 서비스|[추가](http://go.microsoft.com/fwlink/?LinkID=230768)|예|예|  
|Silverlight 1|예|예|예|  
|Silverlight 2|아니요|예|예|  
|Silverlight 3|예|예|예|  
|Silverlight 4|[추가](http://go.microsoft.com/fwlink/?LinkID=153710)|예|예|  
|Silverlight 5|[추가](http://go.microsoft.com/fwlink/?LinkID=215392)\(SP1만 해당\)|예|예|  
|IronPython|[추가](http://go.microsoft.com/fwlink/?LinkID=183863)|[추가](http://go.microsoft.com/fwlink/?LinkID=183863)|[추가](http://go.microsoft.com/fwlink/?LinkID=183863)|  
|IronRuby|[추가](http://go.microsoft.com/fwlink/?LinkID=183864)|[추가](http://go.microsoft.com/fwlink/?LinkID=183864)|[추가](http://go.microsoft.com/fwlink/?LinkID=183864)|  
|Visual Studio Tools for Office|예 <sup>4</sup><br /><br /> \(Office 2007, Office 2010\)|예 <sup>4</sup>\(Office 2010\)|예 <sup>4</sup>\(Office 2013\)|  
|보고서 프로젝트|예|예|예|  
|보고서 마법사|예|예|예|  
|LINQ\(Language\-Integrated Query\)|예|예|예|  
|SharePoint 개발|예\(SharePoint 2010을 대상으로 함\)|예\(SharePoint 2010을 대상으로 함\)|예\(SharePoint 2013을 대상으로 함\)|  
|.NET Framework 4 Client Profile 지원|예|아니요|아니요|  
  
1.  ASP.NET AJAX:  
  
     서버 측: 컨트롤은 ASP.NET 3.5에 포함되어 있으며 Visual Studio의 **도구 상자**에는 이미 있습니다.  ASP.NET 2.0 등 이전 버전의 ASP.NET을 사용하는 경우 [ASP.NET AJAX 확장](http://go.microsoft.com/fwlink/?LinkID=75360)을 다운로드할 수 있습니다.  
  
     클라이언트 측: 클라이언트 측 ASP.NET AJAX 라이브러리는 ASP.NET 3.5 SP1에 포함되어 있습니다.  
  
2.  병렬 컴퓨팅:  
  
     병렬 확장에는 TPL\(작업 병렬 라이브러리\), PLINQ\(병렬 LINQ\) 및 동시성 데이터 구조체가 포함됩니다. 이러한 구성 요소는 .NET Framework 4에 포함되어 있습니다.  네이티브 C\+\+ 개발용 동일한 라이브러리는 동시성 런타임 및 에이전트 라이브러리이며 이러한 라이브러리는 Visual Studio 2010에 포함되어 있습니다.  향상된 프로파일러 및 디버거 기능도 Visual Studio 2010에 포함되어 있습니다.  
  
3.  IronPython 및 IronRuby:  
  
     CodePlex 웹 사이트에서는 IronPython 및 IronRuby용 여러 버전이 제공됩니다.  환경에 적용할 버전을 선택합니다.  두 언어의 최소 요구 사항은 .NET Framework 2.0 SP1입니다.  
  
4.  VSTO\(Visual Studio Tools for Office\) 호환성 및 추가 기능:  
  
    ||Visual Studio 2010|[!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)]|[!INCLUDE[vs_dev12](../data-tools/includes/vs_dev12_md.md)]|  
    |-|------------------------|-------------------------------------------------------------------|--------------------------------------------------------------|  
    |문서 수준|Word 2007, Word 2010, Excel 2007, Excel 2010|Word 2010, Excel 2010|Word 2013, Excel 2013|  
    |응용 프로그램 수준|Word 2007, Word 2010, Excel 2007, Excel 2010, InfoPath 2007, InfoPath 2010, Outlook 2007, Outlook 2010, PowerPoint 2007, PowerPoint 2010, Visio 2007, Visio 2010, Project 2007, Project 2010|Word 2010, Excel 2010, InfoPath 2010, Outlook 2010, PowerPoint 2010, Visio 2010, Project 2010|Word 2013, Excel 2013, InfoPath 2013, Outlook 2013, PowerPoint 2013, Visio 2013, Project 2013|