---
title: "Office 솔루션에서 로컬 데이터베이스 파일 사용 개요"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "데이터[Visual Studio에서 Office 개발], 로컬"
  - "로컬 데이터[Visual Studio에서 Office 개발]"
  - "Office 응용 프로그램[Visual Studio에서 Office 개발], 데이터"
ms.assetid: 7a920e6b-f0c3-4a62-b5dd-02668a6177b6
caps.latest.revision: 30
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 29
---
# Office 솔루션에서 로컬 데이터베이스 파일 사용 개요
  Office 솔루션에서 SQL Server Express \(.mdf\) 파일 또는 Microsoft Office Access \(.mdb\) 파일 등의 데이터베이스 파일을 포함할 수 있습니다.  이렇게 하면 컴퓨터 한 대에서만 사용되는 로컬 재고 관리 솔루션에서처럼 데이터베이스를 중앙에서 관리할 필요가 없는 경우에 최종 사용자가 로컬 데이터베이스를 유지할 수 있습니다.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## 프로젝트에 데이터베이스 파일 가져오기  
 프로젝트에 데이터베이스 파일을 가져오려면 **데이터 소스 구성 마법사**를 사용하여 데이터베이스 파일을 기반으로 한 데이터 소스를 만듭니다.  이 마법사는 데이터베이스 파일과 형식화된 데이터 집합을 프로젝트에 추가합니다.  
  
## 데이터베이스 파일 배포  
 **데이터 소스 구성 마법사**에서는 상대 경로를 사용하여 로컬 데이터베이스 파일에 대한 연결을 만듭니다.  이렇게 하면 파일의 상대 위치를 유지하는 경우 한 컴퓨터의 솔루션을 다른 컴퓨터에 복사할 수 있습니다.  
  
 솔루션을 서버에 배포한 다음 문서를 각 최종 사용자에게 배포하는 경우 데이터베이스 파일도 수동으로 배포하고 이 파일을 문서를 기준으로 동일한 위치에 설치해야 합니다.  즉, 데이터베이스 파일도 함께 옮기지 않는 한 최종 사용자가 자신의 컴퓨터에서 문서를 새 위치로 옮길 수 없습니다.  
  
## 로컬 데이터베이스 파일 및 데이터 집합 캐싱  
 Microsoft Office Excel 및 Microsoft Office Word용 문서 수준 솔루션에서 데이터 집합 인스턴스를 <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute> 특성으로 표시하여 문서의 데이터 집합을 캐시할 수 있습니다.  **데이터 소스 구성 마법사**를 사용하여 프로젝트에 데이터베이스 파일을 추가하면 형식화된 데이터 집합이 프로젝트에 자동으로 추가됩니다.  데이터가 사용자의 컴퓨터에 이미 로컬로 있으므로 이 데이터 집합에 <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute>를 적용해야 할 일은 거의 없습니다.  자세한 내용은 [데이터 캐싱](../vsto/caching-data.md)을 참조하십시오.  
  
## 참고 항목  
 [Office 솔루션의 컨트롤에 데이터 바인딩](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [방법: 데이터베이스의 데이터로 문서 채우기](../vsto/how-to-populate-documents-with-data-from-a-database.md)   
 [방법: Host 컨트롤의 데이터로 데이터 원본 업데이트](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md)   
 [Office 솔루션 배포](../vsto/deploying-an-office-solution.md)   
 [데이터 캐싱](../vsto/caching-data.md)  
  
  