---
title: "Visual Studio 데이터베이스 호환성 | Microsoft Docs"
ms.custom: 
ms.date: 09/06/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- database systems
- database compatibility
- databases for Visual Studio
ms.assetid: 821de34b-eaa9-40af-b9aa-b8305de16899
caps.latest.revision: "28"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: 17bdaffa8fdbb6ddff9d7fe5590db021997aa01f
ms.sourcegitcommit: eb954434c34b4df6fd2264266381b23ce9e6204a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2017
---
# <a name="compatible-database-systems-for-visual-studio"></a>Visual Studio에 대 한 호환 데이터베이스 시스템

Visual Studio에서 데이터에 연결 된 응용 프로그램을 개발 하려면 일반적으로 로컬 개발 컴퓨터에 데이터베이스 시스템을 설치 하 고 배포 응용 프로그램 및 데이터베이스를 프로덕션 환경에 업데이트가 준비 되 면 합니다. Visual Studio 컴퓨터에 SQL Server Express LocalDB의 일부로 설치 된 **데이터 저장 및 처리** 작업 합니다. 이 LocalDB 인스턴스는 쉽고 빠르게 데이터에 연결 된 응용 프로그램을 개발 하는 데 유용 합니다.

.NET 응용 프로그램에서 액세스할 수 있도록 하 고 Visual Studio 데이터 도구 창에 표시 될 데이터베이스 시스템의 경우 ADO.NET 데이터 공급자가 있어야 합니다. 구체적으로 공급자는.NET 응용 프로그램에서 엔터티 데이터 모델을 사용 하려면 Entity Framework을 지원 해야 합니다. 대부분의 공급자는 NuGet 패키지 관리자를 통해 또는 Visual Studio 마켓플레이스를 통해 제공 됩니다.

Azure 저장소 Api를 사용 하는 경우 설치 하 여 Azure 저장소 에뮬레이터 로컬 컴퓨터에서 개발 하는 동안 프로덕션에 배포할 준비가 될 때까지 요금을 방지 하기 위해 합니다. 자세한 내용은 참조 [개발 및 테스트에 Azure 저장소 에뮬레이터를 사용 하 여](https://azure.microsoft.com/en-us/documentation/articles/storage-use-emulator/)합니다.

다음 목록에는 Visual Studio 프로젝트에 사용할 수 있는 더 인기가 데이터베이스 시스템의 일부를 포함 합니다. 이 목록은 완전 한 목록이 없습니다. 목록이 Visual Studio 도구와 완벽 한 통합을 사용 하도록 설정 하는 ADO.NET 데이터 공급자를 제공 하는 공급 업체에 대 한 참조 [ADO.NET 데이터 공급자](https://msdn.microsoft.com/en-us/library/dd363565.aspx)합니다.

## <a name="microsoft-sql-server"></a>Microsoft SQL Server

SQL Server는 Microsoft 주력 데이터베이스 제공 합니다. SQL Server 2016 획기적인 성능, 고급 보안 및 풍부한 통합 보고 및 분석을 제공합니다. 서로 다른 용도로 설계 된 다양 한 버전에 제공 되며:에서 확장성과 성능이 뛰어난 비즈니스 analytics, 단일 컴퓨터에서 사용할 수 있습니다. SQL Server Express는 기록할 재배포 및 포함 하는 SQL Server의 완전 한 기능의 버전입니다.  LocalDB는 구성이 필요 하지 않습니다 하 고 응용 프로그램의 프로세스에서 실행 하는 SQL Server Express의 단순화 된 버전입니다. 제품 중 하나 또는 모두를 다운로드할 수 있습니다 [SQL Server Express 다운로드 페이지](https://www.microsoft.com/en-us/server-cloud/Products/sql-server-editions/sql-server-express.aspx)합니다. 이 섹션의 SQL 예의 여러 SQL Server LocalDB를 사용합니다. SQL Server Management Studio (SSMS)는 Visual Studio SQL Server 개체 탐색기에서 제공 하는 것 보다 더 많은 기능을 가진는 독립 실행형 데이터베이스 관리 응용 프로그램. SSMS는 이전 링크에서 가져올 수 있습니다.

## <a name="oracle"></a>Oracle

Oracle 데이터베이스의 유료 또는 무료 버전을 다운로드할 수 있습니다는 [Oracle 기술 네트워크](http://www.oracle.com/technetwork/database/enterprise-edition/downloads/index-092322.html) 페이지. Entity Framework 및 Tableadapter에 대 한 디자인 타임 지원 해야 합니다는 [Visual Studio 용 Oracle 개발자 도구](http://www.oracle.com/technetwork/developer-tools/visual-studio/overview/index.html)합니다. Oracle 인스턴트 클라이언트를 포함 하 여 다른 공식 Oracle 제품 NuGet 패키지 관리자를 통해 제공 됩니다.  지침에 따라 Oracle 샘플 스키마를 다운로드할 수 있습니다는 [Oracle 온라인 설명서](http://docs.oracle.com/cd/E11882_01/server.112/e10831/toc.htm)합니다.

## <a name="mysql"></a>MySQL

MySQL은 기업과 웹 사이트에서 널리 사용 되는 인기 있는 오픈 소스 데이터베이스 시스템입니다. MySQL에 대 한 다운로드, Visual Studio 및 관련된 제품에 대 한 MySQL 있는 [Windows에서 MySQL](http://www.mysql.com/why-mysql/windows/)합니다.  제 3 자는 다양 한 Visual Studio 확장과 MySQL에 대 한 독립 실행형 관리 응용 프로그램을 제공합니다. NuGet 패키지 관리자에서 제품을 찾아볼 수 있습니다 (**도구** > **NuGet 패키지 관리자** > **솔루션에 대 한 NuGet 패키지 관리**) .

## <a name="postgresql"></a>PostgreSQL

PostgreSQL는 무료 오픈 소스 개체 관계형 데이터베이스 시스템입니다. Windows에 설치 하려면에서 다운로드할 수 있습니다는 [PostgreSQL 다운로드 페이지](http://www.postgresql.org/download/windows/)합니다.  소스 코드에서 PostgreSQL를 빌드할 수도 있습니다.  PostgreSQL 코어 시스템에는 C 언어 인터페이스 포함 되어 있습니다. 많은 타사 PostgreSQL.NET 응용 프로그램에서 사용 하는 NuGet 패키지를 제공 합니다.  NuGet 패키지 관리자에서 제품을 찾아볼 수 있습니다 (**도구** > **NuGet 패키지 관리자** > **솔루션에 대 한 NuGet 패키지 관리**) . 가장 인기 있는 패키지 제공한 아마도 [npgsql.org](http://www.npgsql.org)합니다.

## <a name="sqlite"></a>SQLite

SQLite는 응용 프로그램의 자체 프로세스에서 실행 되는 포함 된 SQL 데이터베이스 엔진입니다. 다운로드할 수는 [SQLite 다운로드 페이지](http://www.sqlite.org/download.html)합니다. SQLite에 대 한 많은 타사 NuGet 패키지를 사용할 수 있습니다. NuGet 패키지 관리자에서 제품을 찾아볼 수 있습니다 (**도구** > **NuGet 패키지 관리자** > **솔루션에 대 한 NuGet 패키지 관리**) .

## <a name="firebird"></a>Firebird

Firebird는 오픈 소스 SQL 데이터베이스 시스템입니다. 다운로드할 수는 [Firebird 다운로드 페이지](http://firebirdsql.org/en/downloads/)합니다. ADO.NET 데이터 공급자는 NuGet 패키지 관리자를 통해 사용할 수 있습니다.

## <a name="see-also"></a>참고 항목

[Visual Studio에서 데이터 액세스](../data-tools/accessing-data-in-visual-studio.md)  
[버전 및 SQL Server 및 해당 구성 요소의 버전을 확인 하는 방법](http://support.microsoft.com/kb/321185)