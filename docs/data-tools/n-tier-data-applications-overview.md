---
title: N 계층 데이터 응용 프로그램 개요
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- presentation tier
- middle tier
- data tier
- n-tier applications, about n-tier applications
ms.assetid: 1020581d-eaaa-41a2-aca4-bf4c212895f6
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 43e75e69899f74fb67980172c546cdc99d41d173
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34747146"
---
# <a name="n-tier-data-applications-overview"></a>N 계층 데이터 응용 프로그램 개요
*N 계층* 데이터 응용 프로그램은 여러도 분리 되어 있는 데이터 응용 프로그램 *계층*합니다. N 계층 응용 프로그램 "분산된 응용 프로그램" 및 "다중 계층 응용 프로그램" 라고도 함, 클라이언트와 서버 간에 배포 된 개별 계층으로 처리를 구분 합니다. 데이터에 액세스 하는 응용 프로그램을 개발 하는 경우 응용 프로그램을 구성 하는 다양 한 계층 간의 분리를 있어야 합니다.

일반적인 n 계층 응용 프로그램에는 프레젠테이션 계층, 중간 계층 및 데이터 계층에 포함 됩니다. N 계층 응용 프로그램에서 다양 한 계층을 분리 하는 가장 쉬운 방법은 응용 프로그램에 포함 시킬 각 계층에 대해 별도 프로젝트를 만드는 것입니다. 예를 들어 프레젠테이션 계층 데이터 액세스 논리는 중간 계층에 있는 클래스 라이브러리 일 수 있습니다는 Windows Forms 응용 프로그램을 수 있습니다. 또한, 프레젠테이션 계층에서 중간 계층 서비스와 같은 서비스를 통해 데이터 액세스 논리와 통신할 수 있습니다. 응용 프로그램 구성 요소를 별도의 계층으로 분리하면 응용 프로그램의 유지 관리성과 확장성이 높아집니다. 전체 솔루션을 다시 디자인할 필요 없이 단일 계층에 적용할 수 있는 새로운 기술을 보다 쉽게 도입할 수 없습니다. 또한 n 계층 응용 프로그램에는 중간 계층 프레젠테이션 계층의 격리를 유지 관리 하는 중요 한 정보를 일반적으로 저장 합니다.

Visual Studio는 개발자가 n 계층 응용 프로그램을 만들 수 있도록 몇 가지 기능이 포함 되어 있습니다.

-   제공 된 **데이터 집합 프로젝트** (데이터 엔터티 계층) 데이터 집합 및 TableAdapters를 분리할 수 있습니다 사용할 수 있는 속성 (데이터 액세스 계층)를 별도 프로젝트로 합니다.

-   [LINQ to SQL 도구 Visual Studio에서](../data-tools/linq-to-sql-tools-in-visual-studio2.md) 별도 네임 스페이스로 DataContext 및 데이터 클래스를 생성 하는 설정을 제공 합니다. 이 통해 데이터 액세스 및 데이터 엔터티 계층의 논리적 분리 합니다.

-   [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index) 제공는 <xref:System.Data.Linq.Table%601.Attach%2A> 메서드를 응용 프로그램에서 다른 계층에서 DataContext를 가져오는 데 사용할 수 있습니다. 자세한 내용은 참조 [N 계층 및 LINQ 사용 하 여 원격 응용 프로그램을 SQL](/dotnet/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql)합니다.

## <a name="presentation-tier"></a>프레젠테이션 계층
*프레젠테이션 계층* 은 사용자가 응용 프로그램 상호 작용 하는 계층입니다. 여기에 포함 된 추가 응용 프로그램 논리도 합니다. 일반적인 프레젠테이션 계층 구성 요소는 다음과 같습니다.

-   바인딩 구성 요소와 같은 데이터는 <xref:System.Windows.Forms.BindingSource> 및 <xref:System.Windows.Forms.BindingNavigator>합니다.

-   같은 개체의 데이터를 표현 [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index) 프레젠테이션 계층에서 사용 하기 위해 엔터티 클래스입니다.

프레젠테이션 계층 서비스 참조를 사용 하 여 일반적으로 중간 계층에 액세스 (예를 들어 한 [Windows Communication Foundation 서비스 및 Visual Studio에서 WCF Data Services](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md) 응용 프로그램). 프레젠테이션 계층 데이터 계층을 직접 액세스 하지 않습니다. 프레젠테이션 계층 중간 계층에서 데이터 액세스 구성 요소를 통해 데이터 계층과 통신합니다.

## <a name="middle-tier"></a>중간 계층
*중간 계층* 서로 통신 하는 데 사용 프레젠테이션 계층과 데이터 계층이 하는 계층입니다. 일반적인 중간 계층 구성 요소는 다음과 같습니다.

-   비즈니스 규칙 및 데이터 유효성 검사 등의 비즈니스 논리

-   데이터 액세스 구성 요소는 다음과 같은 논리 있습니다.

    -   [Tableadapter](create-and-configure-tableadapters.md) 및 [Dataadapter 및 Datareader](/dotnet/framework/data/adonet/dataadapters-and-datareaders)합니다.

    -   같은 개체의 데이터를 표현 [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index) 엔터티 클래스입니다.

    -   일반적인 응용 프로그램 서비스, 개인 설정, 인증 및 권한 부여, 등입니다.

다음은 기능 및 Visual Studio에서 사용할 수 있는 수에 맞는 n 계층 응용 프로그램의 중간 계층 및 기술입니다.

![중간 계층 구성 요소](../data-tools/media/ntiermid.png) 중간 계층

일반적으로 중간 계층 데이터 연결을 사용 하 여 데이터 계층에 연결 합니다. 이 데이터 연결 대개 데이터 액세스 구성 요소에 저장 됩니다.

## <a name="data-tier"></a>데이터 계층
*데이터 계층* 는 기본적으로 응용 프로그램의 데이터를 저장 하는 서버 (예를 들어 실행 하는 서버 [!INCLUDE[ssNoVersion](../data-tools/includes/ssnoversion_md.md)]).

다음은 기능 및 Visual Studio에서 사용할 수 있는 수에 맞는 n 계층 응용 프로그램의 데이터 계층 및 기술입니다.

![데이터 계층 구성 요소](../data-tools/media/ntierdatatier.png) 데이터 계층

데이터 계층 프레젠테이션 계층에 클라이언트에서 직접 액세스할 수 없습니다. 대신, 중간 계층에서 데이터 액세스 구성 요소 프레젠테이션 및 데이터 계층 간의 통신에 사용 됩니다.

## <a name="help-for-n-tier-development"></a>N 계층 개발에 대 한 도움말
다음 항목에 n 계층 응용 프로그램으로 작업 하는 방법에 대 한 정보가 표시 됩니다.

[데이터 집합 및 TableAdapter를 다른 프로젝트로 분리](../data-tools/separate-datasets-and-tableadapters-into-different-projects.md)

[연습: N 계층 데이터 응용 프로그램 만들기](../data-tools/walkthrough-creating-an-n-tier-data-application.md)

[LINQ to SQL을 사용한 N 계층 및 원격 응용 프로그램](/dotnet/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql)

## <a name="see-also"></a>참고자료

- [연습: N 계층 데이터 응용 프로그램 만들기](../data-tools/walkthrough-creating-an-n-tier-data-application.md)
- [계층적 업데이트](../data-tools/hierarchical-update.md)
- [Visual Studio의 데이터 집합 도구](../data-tools/dataset-tools-in-visual-studio.md)
- [Visual Studio에서 데이터 액세스](../data-tools/accessing-data-in-visual-studio.md)