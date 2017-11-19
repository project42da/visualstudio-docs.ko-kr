---
title: "방법: MSBuild 작업을 사용 하 여 SharePoint 솔루션 패키지 만들기 | Microsoft Docs"
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
- VB
- CSharp
helpviewer_keywords: SharePoint development in Visual Studio, packages
ms.assetid: c3880bdd-f0a1-4d53-9a97-5767cb3f7b8e
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 3cfe26fde4dd2d2b6617a008769fd535bb3e2cbb
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-create-a-sharepoint-solution-package-by-using-msbuild-tasks"></a>방법: MSBuild 작업을 사용하여 SharePoint 솔루션 패키지 만들기
  빌드, 정리 및 명령줄 MSBuild 작업을 사용 하 여 개발 컴퓨터에서 SharePoint 패키지 (.wsp) 유효성을 검사할 수 있습니다. 또한 빌드 컴퓨터에서 Team Foundation Server를 사용 하 여 빌드 프로세스를 자동화 하기 이러한 명령을 사용할 수 있습니다.  
  
## <a name="building-a-sharepoint-package"></a>SharePoint 패키지 빌드  
  
#### <a name="to-build-a-sharepoint-package"></a>SharePoint 패키지를 빌드하려면  
  
1.  Windows **시작** 메뉴 선택 **모든 프로그램**, **액세서리**, **명령 프롬프트**합니다.  
  
2.  SharePoint 프로젝트에 위치한 디렉터리로 변경 합니다.  
  
3.  프로젝트에 대 한 패키지를 만들려면 다음 명령을 입력 합니다. 대체 *ProjectFileName* 프로젝트의 이름으로 합니다.  
  
    ```  
    msbuild /t:Package ProjectFileName  
    ```  
  
     예를 들어 ListDefinition1 라는 SharePoint 프로젝트를 패키지 하려면 다음 명령 중 하나를 실행할 수 있습니다.  
  
    ```  
    msbuild /t:Package ListDefinition1.vbproj  
    msbuild /t:Package ListDefinition1.csproj  
    ```  
  
## <a name="cleaning-a-sharepoint-package"></a>SharePoint 패키지를 정리합니다.  
  
#### <a name="to-clean-a-sharepoint-package"></a>SharePoint 패키지를 정리 하려면  
  
1.  명령 프롬프트 창을 엽니다.  
  
2.  SharePoint 프로젝트에 위치한 디렉터리로 변경 합니다.  
  
3.  프로젝트에 대 한 패키지를 정리 하려면 다음 명령을 입력 합니다. 대체 *ProjectFileName* 프로젝트의 이름으로 합니다.  
  
    ```  
    msbuild /t:CleanPackage ProjectFileName  
    ```  
  
     예를 들어 ListDefinition1 라는 SharePoint 프로젝트를 정리 하려면 다음 명령 중 하나를 실행할 수 있습니다.  
  
    ```  
    msbuild /t:CleanPackage ListDefinition1.vbproj  
    msbuild /t:CleanPackage ListDefinition1.csproj  
    ```  
  
## <a name="validating-a-sharepoint-package"></a>SharePoint 패키지 유효성 검사  
  
#### <a name="to-validate-a-sharepoint-package"></a>SharePoint 패키지의 유효성을 검사 하려면  
  
1.  명령 프롬프트 창을 엽니다.  
  
2.  SharePoint 프로젝트에 위치한 디렉터리로 변경 합니다.  
  
3.  프로젝트에 대 한 패키지의 유효성을 검사 하려면 다음 명령을 입력 합니다. 대체 *ProjectFileName* 프로젝트의 이름으로 합니다.  
  
    ```  
    msbuild /t:ValidatePackage ProjectFileName  
    ```  
  
     예를 들어 ListDefinition1 라는 SharePoint 프로젝트의 유효성을 검사 하려면 다음 명령 중 하나를 실행할 수 있습니다.  
  
    ```  
    msbuild /t:ValidatePackage ListDefinition1.vbproj  
    msbuild /t:ValidatePackage ListDefinition1.csproj  
    ```  
  
## <a name="setting-properties-in-a-sharepoint-package"></a>SharePoint 패키지의 속성을 설정합니다.  
  
#### <a name="to-set-a-property-in-a-sharepoint-package"></a>SharePoint 패키지의 속성을 설정 하려면  
  
1.  명령 프롬프트 창을 엽니다.  
  
2.  SharePoint 프로젝트에 위치한 디렉터리로 변경 합니다.  
  
3.  프로젝트에 대 한 패키지의 속성을 설정 하려면 다음 명령을 입력 합니다. 대체 *PropertyName* 속성을 설정 하려면을 사용 합니다.  
  
    ```  
    msbuild /property:PropertyName=Value  
    ```  
  
     예를 들어 경고 수준을 설정 하려면 다음 명령을 실행할 수 있습니다.  
  
    ```  
    msbuild /property:WarningLevel = 2  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 기능 만들기](../sharepoint/creating-sharepoint-features.md)   
 [방법: SharePoint 기능을 사용자 지정](../sharepoint/how-to-customize-a-sharepoint-feature.md)   
 [방법: SharePoint 기능에 항목 추가 및 제거](../sharepoint/how-to-add-and-remove-items-to-sharepoint-features.md)  
  
  