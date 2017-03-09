---
title: "Creating and Managing Databases and Data-tier Applications in Visual Studio | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "managing change, databases"
  - "database features of Visual Studio, managing change"
  - "databases, managing change"
  - "managing change, database servers"
ms.assetid: 40b51f5a-d52c-44ac-8f84-037a0917af33
caps.latest.revision: 37
caps.handback.revision: 35
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Creating and Managing Databases and Data-tier Applications in Visual Studio
> [!IMPORTANT]
>  데이터베이스 프로젝트의 이전 버전에 포함 된 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 에서 이제 제공 [!INCLUDE[sql_Denali_long](../data-tools/includes/sql_denali_long_md.md)] 도구.  자세한 내용은 [SQL Server 개발자 도구](http://go.microsoft.com/fwlink/?LinkId=228126).  
  
 데이터베이스 프로젝트를 사용하여 새 데이터베이스와 새 DAC\(데이터 계층 응용 프로그램\)를 만들고 기존 데이터베이스와 데이터 계층 응용 프로그램을 업데이트할 수 있습니다.  데이터베이스 프로젝트와 DAC 프로젝트는 모두 관리 코드나 네이티브 코드에 버전 제어 및 프로젝트 관리 기술을 적용할 때와 거의 동일한 방식으로 이들 기술을 데이터베이스 개발 작업에 적용할 수 있도록 지원합니다.  *DAC 프로젝트*, *데이터베이스 프로젝트* 또는 *서버 프로젝트*를 만든 후 버전 제어에서 관리하도록 설정하여 개발 팀이 데이터베이스 및 데이터베이스 서버의 변경 내용을 손쉽게 관리하도록 지원할 수 있습니다.  그러면 팀 멤버는 파일을 체크 아웃하여 *격리된 개발 환경*이나 샌드박스에서 파일을 변경하고 변경 내용을 빌드 및 테스트한 후 팀과 공유할 수 있습니다.  코드의 품질을 보장하기 위해 팀에서는 변경 내용을 프로덕션 환경에 배포하기 전에 특정 데이터베이스 릴리스의 모든 변경 내용을 스테이징 환경에서 수행하고 테스트할 수 있습니다.  
  
 데이터 계층 응용 프로그램에서 지원 되는 데이터베이스 기능 목록을 참조 하십시오. [기능을 지 원하는 데이터 계층 응용 프로그램에서](http://go.microsoft.com/fwlink/?LinkId=164239) Microsoft 웹 사이트에서.  데이터 계층 응용 프로그램에서 지원하지 않는 기능을 데이터베이스에서 사용할 경우 대신 데이터베이스 프로젝트를 사용하여 데이터베이스의 변경 내용을 관리해야 합니다.  
  
## 일반 고급 작업  
  
|고급 작업|지원 내용|  
|-----------|-----------|  
|**데이터 계층 응용 프로그램 개발 시작:** DAC는 [!INCLUDE[sskatmai_r2](../data-tools/includes/sskatmai_r2_md.md)]에서 새롭게 소개된 개념으로서 [!INCLUDE[ssNoVersion](../data-tools/includes/ssnoversion_md.md)] 데이터베이스의 정의와 클라이언트\-서버 또는 3계층 응용 프로그램에서 사용하는 지원 인스턴스 개체를 포함하고 있습니다.  DAC에는 테이블 및 뷰 등의 데이터베이스 개체와 로그인 등의 인스턴스 엔터티가 포함됩니다.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]를 사용하여 DAC 프로젝트를 만들고, DAC 패키지 파일을 빌드하고, 이 DAC 패키지 파일을 데이터베이스 관리자에게 보내 [!INCLUDE[ssNoVersion](../data-tools/includes/ssnoversion_md.md)] 데이터베이스 엔진의 인스턴스에 배포하도록 할 수 있습니다.|-   [데이터 계층 응용 프로그램 만들기 및 관리](http://go.microsoft.com/fwlink/?LinkId=160741)\(Microsoft 웹 사이트\)<br />-   [SQL Server Management Studio](http://go.microsoft.com/fwlink/?LinkId=227328)|  
|**반복 개발 작업 수행:** 개발자나 테스터는 프로젝트의 부분들을 체크아웃하여 격리된 개발 환경에서 업데이트합니다.  이 환경 유형을 사용 하 여 팀의 다른 구성원에 영향을 주지 않고 변경 내용을 테스트할 수 있습니다.  변경이 완료된 후 파일을 다시 버전 제어에 체크 인합니다. 그러면 다른 팀 멤버가 변경 내용을 가져와 이를 빌드하고 테스트 서버에 배포할 수 있습니다.|-   [쿼리 및 텍스트 편집기 \(SQL Server Management Studio\)](http://go.microsoft.com/fwlink/?LinkId=227327) \(Microsoft 웹 사이트\)<br />-   [디버거 관리법 SQL](http://go.microsoft.com/fwlink/?LinkId=227324) \(Microsoft 웹 사이트\)|  
|**프로토타입 만들기, 테스트 결과 확인, 데이터베이스 스크립트 및 개체 수정:** [!INCLUDE[tsql](../data-tools/includes/tsql_md.md)] 편집기를 사용하여 이러한 일반적인 작업을 수행할 수 있습니다.|-   [쿼리 및 텍스트 편집기 \(SQL Server Management Studio\)](http://go.microsoft.com/fwlink/?LinkId=227327) \(Microsoft 웹 사이트\)|