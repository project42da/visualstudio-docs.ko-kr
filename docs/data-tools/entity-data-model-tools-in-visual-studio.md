---
title: Visual Studio에서 entity Framework 도구 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 1b06b573-84aa-4458-b3f5-e238df47bf45
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: c9335e5d5bba077a2fd517e80398fa452718fed3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="entity-framework-tools-in-visual-studio"></a>Visual Studio에서 entity Framework 도구
Entity Framework는.NET 개발자가 도메인별 개체를 사용 하 여 관계형 데이터에 사용할 수 있는 개체-관계형 매핑 기술. 개발자들이 보통 작성해야 하는 데이터 액세스 코드가 대부분 필요하지 않게 됩니다. Entity Framework는 새로운.NET 응용 프로그램에 대 한 기술 모델링 권장된 개체-관계형 매핑을 (ORM).  
  
Entity Framework 도구는 Entity Framework (EF) 응용 프로그램을 빌드할 수 있도록 설계 되었습니다. Entity Framework에 대 한 전체 설명서는 여기: [EF 코어 및 EF 6](/ef/)합니다.  
  
Entity Framework 도구를 만들 수 있습니다는 *개념적 모델* 기존 데이터베이스 및 다음 그래픽으로 시각화 하 고 개념적 모델을 편집 합니다. 또는 먼저 개념적 모델을 그래픽으로 만든 후 모델을 지원하는 데이터베이스를 생성할 수 있습니다. 이 두 경우 모두 기본 데이터베이스가 변경될 때 모델을 자동으로 업데이트하고 응용 프로그램에 대한 개체 계층 코드를 자동으로 생성할 수 있습니다. 데이터베이스 생성 및 개체 계층 코드 생성 작업은 사용자 지정할 수 있습니다.  
  
Entity Framework 도구의 일부로 설치 되는 **데이터 저장 및 처리** Visual Studio 설치 관리자에서 작업 합니다. 아래 indvidual 구성 요소로 설치할 수 있습니다는 **Sdk, 라이브러리 및 프레임 워크** 범주입니다.  
 
다음은 Visual Studio에서 Entity Framework 도구를 구성 하는 특정 도구입니다.  
  
-   사용할 수는 [!INCLUDE[vstecado](../data-tools/includes/vstecado_md.md)]  **[!INCLUDE[adonet_edm](../data-tools/includes/adonet_edm_md.md)] 디자이너** (**Entity Designer**)을 시각적으로 만들고 엔터티, 연결, 매핑 및 상속 관계를 수정 합니다. **Entity Designer** 도 생성 [!INCLUDE[TLA#tla_cshrp](../data-tools/includes/tlasharptla_cshrp_md.md)] 또는 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 개체 계층 코드입니다.  
  
-   사용할 수는  **[!INCLUDE[adonet_edm](../data-tools/includes/adonet_edm_md.md)] 마법사** 기존 데이터베이스에서 개념적 모델을 생성 하 여 응용 프로그램에 데이터베이스 연결 정보를 추가 합니다.  
  
-   사용할 수는 **데이터베이스 만들기 마법사** 을 먼저 개념적 모델을 만들고 다음 모델을 지 원하는 데이터베이스를 만듭니다.  
  
-   사용할 수는 **모델 업데이트 마법사** 를 내부 데이터베이스에 변경 된 경우 개념적 모델, 저장소 모델 및 매핑을 업데이트 합니다.  
  
    > [!NOTE]
    >  Visual Studio 2010 이상에서는 Entity Framework 도구 지원 하지 않는 [!INCLUDE[ss2k](../data-tools/includes/ss2k_md.md)]합니다.  
  
도구 생성 하거나.edmx 파일을 수정 합니다. 이.edmx 파일에는 개념적 모델, 저장소 모델 간의 매핑을 설명 하는 정보가 포함 됩니다. 자세한 내용은 참조 [EDMX](https://msdn.microsoft.com/data/jj650889.aspx)합니다.  
  
[Entity Framework 파워 도구](https://marketplace.visualstudio.com/items?itemName=EntityFrameworkTeam.EntityFrameworkPowerToolsBeta4) 엔터티 데이터 모델을 사용 하는 응용 프로그램을 빌드할 수 있습니다. 파워 도구 수 개념적 모델을 생성, 기존 모델의 유효성을 검사, 개념적 모델을 기반으로 하는 개체 클래스를 포함 하는 소스 코드 파일을 생성 및 모델을 생성 하는 뷰를 포함 하는 소스 코드 파일을 생성 합니다. 자세한 내용은 참조 [Pre-Generated 매핑 뷰](https://msdn.microsoft.com/data/dn469601.aspx)합니다.  
  
## <a name="related-topics"></a>관련 항목  
  
|제목|설명|  
|-----------|-----------------|  
|[ADO.NET Entity Framework](/dotnet/framework/data/adonet/ef/index)|사용 하는 방법에 설명 [!INCLUDE[adonet_edm](../data-tools/includes/adonet_edm_md.md)] 도구는 [!INCLUDE[adonet_ef](../data-tools/includes/adonet_ef_md.md)] 응용 프로그램을 만드는 제공 합니다.|  
|[엔터티 데이터 모델](/dotnet/framework/data/adonet/entity-data-model)|링크 및 데이터 기반 응용 프로그램에서 사용 되는 작업에 대 한 정보 제공 [!INCLUDE[adonet_ef](../data-tools/includes/adonet_ef_md.md)]합니다.|  
|[Entity Framework (EF) 설명서)](https://msdn.microsoft.com/library/ee712907(v=vs.113).aspx)|비디오, 자습서 및 Entity Framework를 최대한 활용할 수 있도록 고급 설명서의 인덱스를 제공 합니다.|  
|[ASP.NET 5 응용 프로그램을 새 데이터베이스](https://docs.efproject.net/en/latest/platforms/aspnetcore/new-db.html)|Entity Framework 7을 사용 하 여 새 ASP.NET 5 응용 프로그램을 만드는 방법을 설명 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [.NET용 Visual Studio 데이터 도구](../data-tools/visual-studio-data-tools-for-dotnet.md)