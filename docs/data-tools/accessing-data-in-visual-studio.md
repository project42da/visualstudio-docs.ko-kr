---
title: "Visual Studio에서 데이터 액세스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: "80025080"
helpviewer_keywords:
- data [Visual Studio]
- data access [Visual Studio]
- data [C#]
- ADO.NET, data access
caps.latest.revision: "100"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: c3777249948ba4be917de4ec6c139e7a15bce0a7
ms.sourcegitcommit: 5f436413bbb1e8aa18231eb5af210e7595401aa6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2018
---
# <a name="accessing-data-in-visual-studio"></a>Visual Studio에서 데이터 액세스

Visual Studio에서 거의 모든 데이터베이스 제품 또는 서비스의 형식으로 모든 위치에서 데이터에 연결 하는 응용 프로그램을 만들 수 있습니다-로컬 컴퓨터에서 로컬 영역 네트워크에서 또는 public, private 또는 하이브리드 클라우드에 있습니다.

JavaScript, Python, PHP, Ruby, 또는 c + +에서 응용 프로그램의 경우에 연결한 데이터 때와 마찬가지로 다른 것 라이브러리 구해서 코드를 작성 합니다. Visual Studio.NET 응용 프로그램에 대 한 데이터 원본을 탐색 하 고 저장과 데이터를 메모리에 조작 사용자 인터페이스에 데이터 바인딩 개체 모델을 만들어 사용할 수 있는 도구를 제공 합니다. Microsoft Azure는 Azure 저장소에 연결 하기 위한.NET, Java, Node.js, PHP, Python, Ruby, 모바일 앱 및 Visual Studio의 도구에 대 한 Sdk를 제공 합니다.

다음 목록에서는 Visual Studio에서 사용할 수 있는 많은 데이터베이스 및 저장소 시스템의 일부를 보여 줍니다. [Microsoft Azure](https://azure.microsoft.com/) 제공은 모든 프로 비전 및 관리의 기본 데이터 저장소를 포함 하는 데이터 서비스입니다.  [Azure Tools for Visual Studio](https://www.visualstudio.com/features/azure-tools-vs.aspx) Visual Studio에서 직접 Azure 데이터 저장소로 작업할 수 있도록 선택적 구성 요소입니다. 대부분의 다른 SQL 및 NoSQL 데이터베이스 제품을 여기에 나열 되는 로컬 컴퓨터에서 로컬 네트워크에서 또는 Microsoft Azure에서 가상 컴퓨터에 호스팅할 수 있습니다. 이 시나리오에서는 있습니다은 데이터베이스 자체를 관리 하는 일을 담당 합니다.

**Microsoft Azure**

||||
|-|-|-|
|SQL 데이터베이스|DocumentDB|저장소 (blob, 테이블, 큐, 파일)|
|SQL 데이터 웨어하우스|SQL Server 스트레치 데이터베이스|StorSimple|

기타...

**SQL**

||||
|-|-|-|
|SQL Server 2005-2016, Express 및 LocalDB를 포함 하 여|Firebird|MariaDB|
|MySQL|Oracle|PostgreSQL|
|SQLite|||

기타...

**NoSQL**

||||
|-|-|-|
|Apache Cassandra|CouchDB|MongoDB|
|NDatabase|OrientDB|RavenDB|
|VelocityDB|||

기타...

많은 데이터베이스 공급 업체 및 제 3 자 NuGet 패키지에서 Visual Studio 통합을 지원 합니다. Nuget.org 또는 Visual Studio에서 NuGet 패키지 관리자를 통해 제품을 탐색할 수 있습니다 (**도구** > **NuGet 패키지 관리자** > **NuGet 관리 솔루션에 대 한 패키지**). 다른 데이터베이스 제품 Visual Studio 확장으로 통합합니다. 로 이동 하 여 이러한 제공 되는 Visual Studio 마켓플레이스를 찾아볼 수 **도구**, **확장명 및 업데이트** 다음를 선택 하 고 **온라인** 의 왼쪽된 창에는 대화 상자입니다. 자세한 내용은 참조 [Visual Studio에 대 한 호환 데이터베이스 시스템](../data-tools/installing-database-systems-tools-and-samples.md)합니다.

> [!NOTE]
> 2016 년 4 월 12 일에 SQL Server 2005 지원 연장이 종료 되었습니다. Visual Studio 2015 이상에서 데이터 도구는 계속이 날짜 이후 SQL Server 2005와 함께 작동 하지 않을 수도가 있습니다. 자세한 내용은 참조는 [for SQL Server 2005 지원 종료 공지](https://www.microsoft.com/server-cloud/products/sql-server-2005/)합니다.

## <a name="net-languages"></a>.NET 언어

.NET Core에서는 포함 하 여 모든.NET 데이터 액세스 ADO.NET에서는 어떤 유형의 관계형 / 비관계형 데이터 원본에 액세스 하기 위한 인터페이스를 정의 하는 클래스의 집합을 기반으로 합니다. Visual Studio에 여러 가지 도구와 데이터베이스에 연결할 수 있도록 ADO.NET을 사용 하는 디자이너에 데이터를 조작 하 고 사용자에 게 데이터를 표시 합니다. 이 섹션의 설명서에는 이러한 도구를 사용 하는 방법을 설명 합니다. ADO.NET 명령 개체에 대해 직접 프로그래밍할 수 있습니다. ADO.NET Api를 직접 호출 하는 방법에 대 한 자세한 내용은 참조 [ADO.NET](/dotnet/framework/data/adonet/index)합니다.

ASP.NET과 특별히 관련 된 데이터 액세스 설명서를 참조 하십시오. [데이터로 작업](http://www.asp.net/web-forms/overview/presenting-and-managing-data) ASP.NET 사이트의 합니다. Entity Framework를 사용 하 여 ASP.NET mvc에 대 한 자습서를 참조 하십시오. [Entity Framework 6 Code First MVC 5를 사용 하 여 시작](http://www.asp.net/mvc/overview/getting-started/getting-started-with-ef-using-mvc/creating-an-entity-framework-data-model-for-an-asp-net-mvc-application)합니다.

C# 또는 Visual Basic의 유니버설 Windows 플랫폼 (UWP) 앱 Microsoft Azure SDK for.NET을 사용 하 여 Azure 저장소 및 기타 Azure 서비스에 액세스할 수 있습니다. Windows.Web.HttpClient 클래스 RESTful 서비스와 통신할 수 있도록 합니다. 자세한 내용은 참조 [Windows.Web.Http를 사용 하 여 HTTP 서버에 연결 하는 방법을](https://msdn.microsoft.com/library/windows/apps/dn469430.aspx)합니다.

로컬 컴퓨터에서 데이터 저장소에 대 한 앱과 동일한 프로세스에서 실행 되는 SQLite를 사용 하는 것이 좋습니다. 개체-관계형 매핑 (ORM) 계층을 필요한 경우에 Entity Framework를 사용할 수 있습니다. 자세한 내용은 참조 [데이터 액세스](https://msdn.microsoft.com/windows/uwp/data-access/index) Windows 개발자 센터에서.

Azure 서비스에 연결 하는 경우 다운로드 해야 최신 [Azure SDK 도구](https://azure.microsoft.com/downloads/)합니다.

### <a name="data-providers"></a>데이터 공급자

ADO.NET에서 사용할 수 있으려면 데이터베이스에 대 한 사용자 지정 있어야 *ADO.NET 데이터 공급자* 또는 다른 ODBC 또는 OLE DB 인터페이스를 노출 해야 합니다. Microsoft가 제공 된 [ADO.NET 데이터 공급자의 목록](https://msdn.microsoft.com/data/dd363565) ODBC 및 OLE DB 공급자 뿐만 아니라 SQL Server 제품에 대 한 합니다.

### <a name="data-modeling"></a>데이터 모델링

.NET, 모델링 및 데이터 원본에서 검색 한 후 메모리에서 데이터를 조작 하기 위한 세 가지 선택 옵션이 있습니다.

[Entity Framework](../data-tools/entity-data-model-tools-in-visual-studio.md)  
기본 Microsoft ORM 기술입니다. .NET 개체로 나타나므로 관계형 데이터에 대 한 프로그램에 사용할 수 있습니다. 새 응용 프로그램에 대 한 모델은 필요한 경우 첫 번째 기본 선택 이어야 합니다. 기본 ADO.NET 공급자의 사용자 지정 지원이 필요합니다.

[LINQ to SQL](../data-tools/linq-to-sql-tools-in-visual-studio2.md)  
이전 세대 개체 관계형 매퍼입니다. 이 덜 복잡 한 시나리오에 적합 하지만 더 이상 개발 합니다.

[데이터 집합](../data-tools/dataset-tools-in-visual-studio.md)  
가장 오래 된 세 가지 모델링 기술 중입니다. "데이터 폼" 응용 프로그램은 하지 많은 양의 데이터를 처리 하거나 없는 복잡 한 쿼리 또는 변환을 수행의 신속한 개발을 위한 주로 설계 되었습니다. 논리적으로 SQL 데이터베이스 개체를.NET 개체 보다 훨씬 더 비슷한 DataTable 및 DataRow 개체의 DataSet 개체로 구성 됩니다. SQL 데이터 원본을 기반으로 비교적 간단한 응용 프로그램, 데이터 집합에 적합 한 선택 중일 수 있습니다.

이러한 기술 중 하나를 사용 하는 요구 사항이 있습니다. 일부 시나리오에서는 성능 상태가 심각 하면 경우에 특히 있습니다 수을 사용 하 여 DataReader 개체를 데이터베이스에서 읽고 목록과 같은 컬렉션 개체에 필요한 값을 복사\<T >.

## <a name="native-c"></a>네이티브 C++

SQL Server에 연결 하는 c + + 응용 프로그램을 사용할지는 [SQL Server 용 Microsoft® ODBC Driver 13.1](https://www.microsoft.com/download/details.aspx?id=53339) 대부분의 경우에서. 서버가 연결 되어 OLE DB는 필요한 고에 대 한 사용는 [SQL Server Native Client](/sql/relational-databases/native-client/sql-server-native-client)합니다. 사용 하 여 다른 데이터베이스에 액세스할 수 있습니다 [ODBC](https://msdn.microsoft.com/library/ms710252\(v=vs.85\).aspx) 또는 OLE DB 드라이버 직접 합니다. ODBC는 현재 표준 데이터베이스 인터페이스 하지만 대부분의 데이터베이스 시스템 ODBC 인터페이스를 통해 액세스할 수 없는 사용자 지정 기능을 제공 합니다. OLE DB는 계속 지원 하지만 새 응용 프로그램에는 권장 되지 않는 레거시 COM 데이터 액세스 기술입니다. 자세한 내용은 참조 [Visual c + +에서 데이터 액세스](/cpp/data/data-access-in-cpp)합니다.

REST 서비스를 사용 하는 c + + 프로그램에서 사용할 수는 [c + + REST SDK](https://github.com/Microsoft/cpprestsdk)합니다.

Microsoft Azure 저장소를 사용 하는 c + + 프로그램에서 사용할 수는 [Microsoft Azure 저장소 클라이언트](http://www.nuget.org/packages/wastorage)합니다.

데이터 모델링&mdash;Visual Studio c + +에 대 한 ORM 계층을 제공 하지 않습니다. [ODB](http://www.codesynthesis.com/products/odb/) 인기 있는 오픈 소스 ORM을 c + +입니다.

C + + 응용 프로그램에서 데이터베이스에 연결 하는 방법에 대 한 자세한 참조 [c + + 용 Visual Studio data tools](../data-tools/visual-studio-data-tools-for-cpp.md)합니다. 레거시 Visual c + + 데이터 액세스 기술에 대 한 자세한 내용은 참조 [데이터 액세스](/cpp/data/data-access-in-cpp)합니다.

## <a name="javascript"></a>JavaScript

[Visual Studio의 JavaScript](/scripting/javascript/javascript-language-reference) 는 플랫폼 간 앱을 UWP 앱, 클라우드 서비스, 웹 사이트 및 웹 응용 프로그램을 구축 하기 위한 첫 번째 클래스는 언어입니다. 즐겨 찾는 JavaScript 라이브러리 및 데이터베이스 제품을 설치 하려면 Bower, Grunt, Gulp, npm 및 Visual Studio 내에서 NuGet을 사용할 수 있습니다. Sdk를 다운로드 하 여 Azure 저장소 및 서비스에 연결 된 [Azure 웹 사이트](https://azure.microsoft.com/)합니다. Edge.js 서버 쪽 JavaScript (Node.js) ADO.NET 데이터 원본에 연결 하는 라이브러리입니다.

## <a name="python"></a>Python

설치 [Python Tools for Visual Studio](http://microsoft.github.io/PTVS/) CPython 또는 IronPython (.NET) 응용 프로그램을 만드는 즐겨 찾는 Python 프레임 워크와 함께 합니다. Python Tools for Visual Studio 웹 사이트에 데이터를 포함 하 여 연결에 대 한 몇 가지 자습서 [Django 및 azure SQL 데이터베이스](https://github.com/Microsoft/PTVS/wiki/Django-and-SQL-Database-on-Azure), [Django 및 Azure에서 MySQL](https://github.com/Microsoft/PTVS/wiki/Django-and-MySQL-on-Azure) 및 [Bottle 및 MongoDB에 Azure](https://github.com/Microsoft/PTVS/wiki/Bottle-and-MongoDB-on-Azure)합니다.

## <a name="related-topics"></a>관련 항목

[데이터, 장치 및 분석](https://msdn.microsoft.com/data-and-devices)  
Cortana Analytics Suite 및 사물 인터넷에 대 한 지원을 포함 하 여 Microsoft intelligent cloud에 대 한 소개를 제공 합니다.

[Microsoft Azure 저장소](https://azure.microCsoft.com/documentation/services/storage/)  
Azure 저장소 및 Azure blob, 테이블, 큐 및 파일을 사용 하 여 응용 프로그램을 만드는 방법에 설명 합니다.

[Azure SQL 데이터베이스](https://azure.microsoft.com/documentation/services/sql-database/)  
Azure SQL 데이터베이스, 서비스는 관계형 데이터베이스에 연결 하는 방법을 설명 합니다.

[SQL Server Data Tools](/sql/ssdt/download-sql-server-data-tools-ssdt)  
디자인, 탐색, 테스트 및 데이터에 연결 된 응용 프로그램 및 데이터베이스의 배포를 단순화 하는 도구에 설명 합니다.

[ADO.NET](/dotnet/framework/data/adonet/index)  
ADO.NET 아키텍처 및 응용 프로그램 데이터를 관리 하 고 데이터 원본 및 XML 상호 작용을 ADO.NET 클래스를 사용 하는 방법을 설명 합니다.

[ADO.NET Entity Framework](https://msdn.microsoft.com/data/ef)  
관계형 데이터베이스에 대해 직접 대신 개념적 모델에 대해 프로그래밍 하는 데 사용할 수 있는 데이터 응용 프로그램을 만드는 방법을 설명 합니다.

[WCF Data Services 4.5](/dotnet/framework/data/wcf/index)  
사용 하는 방법에 설명 [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)] 구현 하는 웹 또는 인트라넷에 데이터 서비스를 배포 하는 [개방형 데이터 프로토콜 (OData)](http://go.microsoft.com/fwlink/?LinkID=182204)합니다.

[Office 솔루션의 데이터](../vsto/data-in-office-solutions.md)  
Office 솔루션에서 데이터가 작동 하는 방법을 설명 하는 항목에 대 한 링크를 포함 합니다. 스키마 지향 프로그래밍, 데이터 캐싱 및 서버 쪽 데이터 액세스에 대 한 정보가 포함 됩니다.

[LINQ(Language-Integrated Query)](/dotnet/csharp/linq/)  
C# 및 Visual Basic 및 관계형 데이터베이스, XML 문서, 데이터 집합 및 메모리 내 컬렉션을 쿼리 하기 위한 일반적인 모델에 내장 된 쿼리 기능을 설명 합니다.

[Visual Studio의 XML 도구](../xml-tools/xml-tools-in-visual-studio.md)  
XML 데이터를 디버깅 XSLT,.NET Framework XML 기능을 사용 하는 작업 및 XML 쿼리 아키텍처에 설명합니다.

[XML 문서 및 데이터](/dotnet/standard/data/xml/index)  
.NET Framework에서 XML 문서 및 데이터로 작업하는 종합적이고 통합된 클래스 집합에 대한 개요를 제공합니다.