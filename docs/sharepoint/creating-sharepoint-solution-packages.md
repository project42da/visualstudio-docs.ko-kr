---
title: "SharePoint 솔루션 패키지 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, packages
- packages [SharePoint development in Visual Studio]
ms.assetid: 6b1f1fbf-fa9c-453d-80af-36ec9829677a
caps.latest.revision: "25"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: f21356c34a94540d20be2bb9fa092bff270f1a70
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="creating-sharepoint-solution-packages"></a>SharePoint 솔루션 패키지 만들기
  패키지 디자이너를 사용 하 여 만들 수 있으며 배포 패키지를 사용자 지정 키를 누릅니다. 예를 들어 SharePoint 프로젝트 항목 및 기능을 IIS 서버를 다시 설정, 기능 활성화 범위를 설정 하 고 기능 종속성을 식별할를 추가할 수 있습니다. 또한이 디자이너는 각 패키지를 설명 하는 XML 파일인 매니페스트를 생성 합니다.  
  
## <a name="packaging-tools"></a>패키징 도구  
 사용할 수는 **패키지 디자이너** 패키지 사용자 지정 하는 매니페스트를 생성 합니다. SharePoint 프로젝트 항목을 포함, 웹 서버를 다시 설정 하 고 배포 서버 유형을 설정 해야 하는지 여부를 구성할 수 있습니다. 자세한 내용은 참조 [하는 방법: 패키지 디자이너를 사용 하 여 패키지에 기능과 항목을 제거 하 고 추가](../sharepoint/how-to-add-and-remove-features-and-items-to-a-package-by-using-the-package-designer.md)합니다.  
  
 사용할 수 있습니다는 **패키징 탐색기** 기능 및 패키지 (.wsp) 파일에 항목을 수정할 수 있습니다. 자세한 내용은 참조 [하는 방법: 패키징 탐색기를 사용 하 여 패키지에 기능과 항목을 제거 하 고 추가](../sharepoint/how-to-add-and-remove-features-and-items-to-a-package-by-using-the-packaging-explorer.md)합니다.  
  
 SharePoint 솔루션을 배포 하려면 패키지 (.wsp) 파일을 만들려면 Visual Studio 및 MSBuild를 사용할 수 있습니다. 이 프로세스는 SharePoint 배포에 필요한 매니페스트 파일을 생성 합니다. 자세한 내용은 참조 [하는 방법: SharePoint 패키지 만들기](http://msdn.microsoft.com/en-us/b24be45c-e91d-49bb-afb0-7b265404214b) 및 [하는 방법: MSBuild 작업을 사용 하 여 SharePoint 솔루션 패키지 만들기](../sharepoint/how-to-create-a-sharepoint-solution-package-by-using-msbuild-tasks.md)합니다.  
  
## <a name="package-designer-options"></a>패키지 디자이너 옵션  
 다음 표에 사용 하 여 SharePoint 패키지에서 사용자 지정할 수 있는 속성이 나와 **패키지 디자이너**합니다.  
  
|패키지 디자이너 속성|기본 설정 설명|  
|-------------------------------|------------------------------------|  
|이름|필수 요소. 패키지의 기본 이름은 설정은 *ProjectName*합니다.|  
|웹 서버를 다시 설정|선택 사항입니다. .Wsp 파일은 SharePoint 서버에 설치 된 후에 웹 서버를 다시 시작 하려는 경우 선택 합니다.|  
|배포 서버 유형|필수 요소. 기본적으로 범위 ApplicationServer로 설정 됩니다.<br /><br /> ApplicationServer: 서비스를 호스팅하는 서버에 설명 합니다.<br /><br /> WebFrontEnd: 웹 사이트를 호스팅하는 서버에 설명 합니다.|  
|솔루션에서 항목|모든 SharePoint 프로젝트 항목 및 패키지에 추가할 수 있는 기능입니다.|  
|패키지의 항목|선택 사항입니다. 모든 SharePoint 항목 및 패키지에 배포 하려는 하는 기능입니다.|  
  
## <a name="configuring-the-packaging-process"></a>패키징 프로세스 구성  
 Visual Studio에서 SharePoint 솔루션을 개발 하는 프로젝트가 패키지 되는 방식을 사용자 지정할 수 있습니다.  
  
 다음 표에서.wsp 파일을 만드는 방법을 사용자 지정 하는 데 사용할 수 있는 두 가지 MSBuild 대상을 보여 줍니다.  
  
|대상|설명|  
|------------|-----------------|  
|BeforeLayout|중간 디렉터리에 파일이 복사 되는 바로 전에 작업을 수행 하는 대상입니다. 패키지 파일 (.wsp)을 만들기 전에 파일을 수정할 수 있습니다.|  
|AfterLayout|중간 디렉터리에 파일이 복사 된 후에 즉시 작업을 수행 하는 대상입니다.|  
  
 자세한 내용은 [하는 방법: MSBuild 대상을 사용 하 여 SharePoint 솔루션 패키지 사용자 지정](../sharepoint/how-to-customize-a-sharepoint-solution-package-by-using-msbuild-targets.md)합니다.  
  
## <a name="packaging-architecture"></a>패키징 아키텍처  
 다음 단계에는 Visual Studio에서 SharePoint 패키지 (.wsp)를 만들 때 발생 합니다.  
  
1.  기능 및 패키지는 패키지의 물리적 및 의미론 구조 정확한 지 확인 유효성이 검사 됩니다.  
  
2.  기능, 프로젝트 항목 및 패키지의 패키지 파일 열거 됩니다. 패키지 및 기능에 대 한 매니페스트 파일 배포 및 정품 인증에 필요한 모든 정보를 포함 하도록 변환 됩니다. 토큰은 정규화 된 값으로 대체 됩니다.  
  
3.  사용자 지정 가능한 BeforeLayout MSBuild 대상 수행 됩니다. .Wsp 파일을 만들기 전에 패키지에 대 한 사용자 지정 수정을 확인 하려면이 단계를 만들 수 있습니다.  
  
4.  열거 되는 파일은 중간 디렉터리에 복사 됩니다.  
  
5.  사용자 지정 가능한 AfterLayout MSBuild 대상 수행 됩니다. .Wsp 파일을 만들기 전에 패키지에 대 한 사용자 지정 수정을 확인 하려면이 단계를 만들 수 있습니다.  
  
6.  중간 디렉터리에 있는 파일.wsp 파일에 추가 됩니다.  
  
## <a name="package-folder-structure"></a>패키지 폴더 구조  
 SharePoint 프로젝트를 압축할 때.wsp 파일 만들어집니다는 SolutionFolder\bin에\\*BuildConfiguration* 폴더입니다. 예를 들어, 솔루션에 있으면 *드라이브*: \Visual Studio 2013\Projects\ListDefinition1 및 빌드 구성을 릴리스로 설정 되어,.wsp 파일에 위치한 *드라이브*: \Visual Studio 2013 \ Projects\ListDefinition1\bin\Release 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: SharePoint 솔루션 패키지 사용자 지정](../sharepoint/how-to-customize-a-sharepoint-solution-package.md)  
 [방법: 추가 및 패키지 디자이너를 사용 하 여 패키지에 기능과 항목 제거](../sharepoint/how-to-add-and-remove-features-and-items-to-a-package-by-using-the-package-designer.md)   
 [방법: SharePoint 패키지 만들기](http://msdn.microsoft.com/en-us/b24be45c-e91d-49bb-afb0-7b265404214b)   
 [방법: MSBuild 작업을 사용 하 여 SharePoint 솔루션 패키지 만들기](../sharepoint/how-to-create-a-sharepoint-solution-package-by-using-msbuild-tasks.md)   
 [방법: MSBuild 대상을 사용하여 SharePoint 솔루션 패키지 사용자 지정](../sharepoint/how-to-customize-a-sharepoint-solution-package-by-using-msbuild-targets.md)  
  
  