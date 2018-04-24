---
title: 데이터베이스 프로젝트, 서버 프로젝트 및 Visual Studio에서 DAC 프로젝트
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- managing change, databases
- database features of Visual Studio, managing change
- databases, managing change
- managing change, database servers
ms.assetid: 40b51f5a-d52c-44ac-8f84-037a0917af33
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: e456d436145d859a24a224511dc69c1383bbcaeb
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="database-projects-and-data-tier-applications-in-visual-studio"></a>데이터베이스 프로젝트와 Visual Studio에서 데이터 계층 응용 프로그램
데이터베이스 프로젝트를 사용 하 여 새 데이터베이스를 만들 새 데이터 계층 응용 프로그램 (Dac)를 기존 데이터베이스 및 데이터 계층 응용 프로그램을 업데이트 합니다. 데이터베이스 프로젝트와 DAC 프로젝트를 사용 거의 동일한 방법으로 관리 또는 네이티브 코드에 이러한 기법을 적용 하는 데이터베이스 개발 작업에 버전 제어 및 프로젝트 관리 기술을 적용할 수 있습니다. 개발 팀을 만들어 데이터베이스 및 데이터베이스 서버에 변경 내용을 관리할 수 있습니다는 *DAC 프로젝트*, *데이터베이스 프로젝트*, 또는 *서버 프로젝트* 를 후 버전 제어 합니다. 팀의 멤버 수 다음 파일을 체크 아웃 확인, 빌드 및에서 변경 내용을 테스트 하는 *격리 된 개발 환경*, 또는 샌드박스는 팀과 공유 하기 전에. 코드 품질을 보장 하기 위해 팀 완료 하 고 프로덕션 환경에 변경 내용을 배포 하기 전에 스테이징 환경에서 데이터베이스의 특정 릴리스에 대 한 모든 변경 내용을 테스트할 수 있습니다.

데이터 계층 응용 프로그램에서 지원 되는 데이터베이스 기능 목록을 보려면 참조 [데이터 계층 응용 프로그램에서 지 원하는 기능](http://go.microsoft.com/fwlink/?LinkId=164239) Microsoft 웹 사이트에 있습니다. 데이터베이스의 데이터 계층 응용 프로그램에서 지원 되지 않는 기능을 사용 하면 데이터베이스에 변경 내용을 관리 하는 데이터베이스 프로젝트를 대신 사용 해야 합니다.

## <a name="common-high-level-tasks"></a>일반 고급 작업

|상위 수준 작업|지원 내용|
|----------------------|------------------------|
|**데이터 계층 응용 프로그램 개발을 시작:** A DAC가 도입 된 새로운 개념을 [!INCLUDE[sskatmai_r2](../data-tools/includes/sskatmai_r2_md.md)] 에 대 한 정의 포함 하는 [!INCLUDE[ssNoVersion](../data-tools/includes/ssnoversion_md.md)] 데이터베이스 및 지원 되는 인스턴스는 클라이언트 서버 또는 3 계층에서 사용 되는 개체 응용 프로그램입니다. DAC에 테이블 및 뷰와 같은 로그인 인스턴스 엔터티가 같은 데이터베이스 개체에 포함 됩니다. 사용할 수 있습니다 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] DAC 프로젝트를 만들려면는 DAC 패키지 파일을 작성 하 고 DAC 패키지 파일의 인스턴스에 배포에 대 한 데이터베이스 관리자에 게 보낼는 [!INCLUDE[ssNoVersion](../data-tools/includes/ssnoversion_md.md)] 데이터베이스 엔진입니다.|-   [데이터 계층 응용 프로그램 만들기 및 관리](http://go.microsoft.com/fwlink/?LinkId=160741) (Microsoft 웹 사이트)<br />-   [SQL Server Management Studio](http://go.microsoft.com/fwlink/?LinkId=227328)|
|**반복 데이터베이스 개발 수행:** 개발자 또는 테스터가 인 경우 프로젝트의 요소를 선택한 후 다음 격리 된 개발 환경에서 업데이트 하 합니다. 이러한 유형의 환경을 사용 하 여 팀의 다른 멤버에 영향을 주지 않고 변경 내용을 테스트할 수 있습니다. 변경이 완료 한 후 다시 여기서 다른 팀 멤버가 변경 내용을 가져올 및 빌드하고 배포할 수에 테스트 서버에 버전 제어에 파일을 확인 합니다.|-   [쿼리 및 텍스트 편집기 (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=227327) (Microsoft 웹 사이트)<br />-   [TRANSACT-SQL 디버거](http://go.microsoft.com/fwlink/?LinkId=227324) (Microsoft 웹 사이트)|
|**프로토타입 생성, 확인 테스트 결과 및 수정 하 고 데이터베이스 스크립트 및 개체:** 사용할 수 있습니다는 [!INCLUDE[tsql](../data-tools/includes/tsql_md.md)] 편집기를 이러한 일반적인 작업 중 하나를 수행 합니다.|-   [쿼리 및 텍스트 편집기 (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=227327) (Microsoft 웹 사이트)|

## <a name="see-also"></a>참고자료

- [.NET용 Visual Studio 데이터 도구](../data-tools/visual-studio-data-tools-for-dotnet.md)
