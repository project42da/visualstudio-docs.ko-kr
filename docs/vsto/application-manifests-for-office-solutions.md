---
title: "Office 솔루션에 대 한 응용 프로그램 매니페스트 | Microsoft Docs"
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
helpviewer_keywords: application manifests [Office development in Visual Studio]
ms.assetid: dd38685f-f429-4a35-8c11-a03372c9770a
caps.latest.revision: "41"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: feda5cbd710ad1d3b7175219261a16f78a774f7d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="application-manifests-for-office-solutions"></a>Office 솔루션의 응용 프로그램 매니페스트
  응용 프로그램 매니페스트는 Microsoft Office 솔루션에 로드된 어셈블리를 설명하는 XML 파일입니다. Visual Studio의 Microsoft Office 개발 도구는 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] 참조에 정의된 [ndptecclick](/visualstudio/deployment/clickonce-application-manifest) 응용 프로그램 매니페스트 스키마를 사용합니다.  
  
 Office 솔루션의 응용 프로그램 매니페스트는 다음 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] 요소와 특성을 사용합니다.  
  
|요소|설명|특성|  
|-------------|-----------------|----------------|  
|[&#60; 어셈블리 &#62; 요소 &#40; ClickOnce 응용 프로그램 &#41;](/visualstudio/deployment/assembly-element-clickonce-deployment)|필수 요소. 최상위 요소입니다.|`manifestVersion`|  
|[&#60; assemblyIdentity &#62; 요소 &#40; ClickOnce 응용 프로그램 &#41;](/visualstudio/deployment/assemblyidentity-element-clickonce-deployment)|필수 요소. [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] 응용 프로그램의 주 어셈블리를 식별합니다.|`name`<br /><br /> `version`<br /><br /> `publicKeyToken`<br /><br /> `processorArchitecture`<br /><br /> `language`|  
|[&#60; trustInfo &#62; 요소 &#40; ClickOnce 응용 프로그램 &#41;](/visualstudio/deployment/trustinfo-element-clickonce-application)|응용 프로그램 보안 요구 사항을 식별합니다.|없음|  
|[&#60; entryPoint &#62; 요소 &#40; ClickOnce 응용 프로그램 &#41;](/visualstudio/deployment/entrypoint-element-clickonce-application)|필수 요소. 실행을 위해 응용 프로그램 코드 진입점을 식별합니다.|`name`<br /><br /> `dependencyName`<br /><br /> `customHostSpecified`|  
|[&#60; 종속성 &#62; 요소 &#40; ClickOnce 응용 프로그램 &#41;](/visualstudio/deployment/dependency-element-clickonce-deployment)|필수 요소. 응용 프로그램을 실행하는 데 필요한 각 종속성을 식별합니다. 필요에 따라 사전 설치해야 하는 어셈블리를 식별합니다.|없음|  
|[&#60; 파일 &#62; 요소 &#40; ClickOnce 응용 프로그램 &#41;](/visualstudio/deployment/file-element-clickonce-application)|필수 요소. 응용 프로그램에서 사용되는 각 비어셈블리 파일을 식별합니다. 파일에 연결된 COM(구성 요소 개체 모델) 격리 데이터를 포함할 수 있습니다.|`name`<br /><br /> `size`|  
  
 Office 솔루션의 응용 프로그램 매니페스트에는 `co.v1` 네임스페이스에 다음과 같은 요소가 있습니다.  
  
```  
<entryPoint>  
    <co.v1:customHostSpecified />  
</entryPoint>   
```  
  
 또한 이러한 응용 프로그램 매니페스트에는 `vstav3` 네임스페이스에 다음과 같은 요소 및 특성도 있습니다.  
  
```  
<addIn>  
  <entryPointsCollection>  
    <entryPoints>  
      <entryPoint>  
      </entryPoint>  
    </entryPoints>  
  </entryPointsCollection>  
  <update></update>  
  <postActions>  
    <postAction>  
      <postActionData>  
      </postActionData>  
    <postAction>  
  </postActions>  
  <application>  
    <customizations>  
      <customization>  
      </customization>  
    </customizations>  
  </application  
</addIn>  
```  
  
|요소|설명|특성|  
|-------------|-----------------|----------------|  
|[&#60; customHostSpecified &#62; 요소 &#40; Visual Studio &#41;에서 Office 개발](../vsto/customhostspecified-element-office-development-in-visual-studio.md)|필수 요소. 매니페스트를 특별히 Office 솔루션으로 표시합니다.|없음|  
|[&#60; 추가 기능 &#62; 요소 &#40; Visual Studio &#41;에서 Office 개발](../vsto/addin-element-office-development-in-visual-studio.md)|필수 요소. 진입점을 단일 네임스페이스에 저장합니다.|없음|  
|[&#60; entryPointsCollection &#62; 요소 &#40; Visual Studio &#41;에서 Office 개발](../vsto/entrypointscollection-element-office-development-in-visual-studio.md)|필수 요소. 하나 이상의 Office 솔루션에 대한 모든 어셈블리를 그룹화합니다.|`id`|  
|[&#60; 진입점 &#62; 요소 &#40; Visual Studio &#41;에서 Office 개발](../vsto/entrypoints-element-office-development-in-visual-studio.md)|필수 요소. Office 솔루션을 실행하는 모든 어셈블리를 그룹화합니다.|없음|  
|[&#60; entryPoint &#62; 요소 &#40; Visual Studio &#41;에서 Office 개발](../vsto/entrypoint-element-office-development-in-visual-studio.md)|필수 요소. Office 솔루션에서 실행하는 어셈블리를 식별합니다.|`class`<br /><br /> `contract`|  
|[&#60; update&#62; 요소 &#40; Visual Studio &#41;에서 Office 개발](../vsto/update-element-office-development-in-visual-studio.md)|필수 요소. 솔루션에 대한 업데이트를 구성합니다.|`enabled`<br /><br /> `expiration`|  
|[&#60; postActions &#62; 요소 &#40; Visual Studio &#41;에서 Office 개발](../vsto/postactions-element-office-development-in-visual-studio.md)|선택 사항입니다. Office 솔루션을 설치한 후 실행하는 모든 배포 후 작업을 그룹화합니다.|없음|  
|[&#60; postAction &#62; 요소 &#40; Visual Studio &#41;에서 Office 개발](../vsto/postaction-element-office-development-in-visual-studio.md)|선택 사항입니다. 배포 후 작업을 식별합니다.|없음|  
|[&#60; postActionData &#62; 요소 &#40; Visual Studio &#41;에서 Office 개발](../vsto/postactiondata-element-office-development-in-visual-studio.md)|선택 사항입니다. 배포 후 작업에 대한 데이터를 구성합니다.|없음|  
|[&#60; 응용 프로그램 &#62; 요소 &#40; Visual Studio &#41;에서 Office 개발](../vsto/application-element-office-development-in-visual-studio.md)|필수 요소. 응용 프로그램 관련 정보를 단일 노드에 래핑합니다.|없음|  
|[&#60; 사용자 지정 &#62; 요소 &#40; Visual Studio &#41;에서 Office 개발](../vsto/customizations-element-office-development-in-visual-studio.md)|필수 요소. 별도의 네임스페이스에 모든 응용 프로그램 호스트 관련 정보를 저장합니다.|없음|  
|[&#60; 사용자 지정 &#62; 요소 &#40; Visual Studio &#41;에서 Office 개발](../vsto/customization-element-office-development-in-visual-studio.md)|필수 요소. 별도의 네임스페이스에 응용 프로그램 호스트 관련 정보를 저장합니다.|`xmlns`|  
|[&#60; 문서 &#62; 요소 &#40; Visual Studio &#41;에서 Office 개발](../vsto/document-element-office-development-in-visual-studio.md)|문서 수준 솔루션에 대해서만 필수 요소. 사용자 지정 관련 정보를 저장합니다.|`solutionId`|  
|[&#60; appAddin &#62; 요소 &#40; Visual Studio &#41;에서 Office 개발](../vsto/appaddin-element-office-development-in-visual-studio.md)|응용 프로그램 수준 솔루션에 대해서만 필수 요소. 사용자 지정 관련 정보를 저장합니다.|`application`<br /><br /> `loadBehavior`<br /><br /> `keyName`|  
|[&#60; friendlyName &#62; 요소 &#40; Visual Studio &#41;에서 Office 개발](../vsto/friendlyname-element-office-development-in-visual-studio.md)|선택 사항입니다. 설치된 VSTO 추가 기능 목록에 표시되는 VSTO 추가 기능의 이름을 저장합니다.|없음|  
|[&#60; 설명 &#62; 요소 &#40; Visual Studio &#41;에서 Office 개발](../vsto/description-element-office-development-in-visual-studio.md)|VSTO 추가 기능에 대해서만 필수 요소. 설치된 프로그램 목록에 나타나는 설명을 저장합니다.|없음|  
|[&#60; formRegions &#62; 요소 &#40; Visual Studio &#41;에서 Office 개발](../vsto/formregions-element-office-development-in-visual-studio.md)|양식 영역을 포함하는 Outlook VSTO 추가 기능에 대해서만 필수 요소.|없음|  
|[&#60; formRegion &#62; 요소 &#40; Visual Studio &#41;에서 Office 개발](../vsto/formregion-element-office-development-in-visual-studio.md)|양식 영역을 포함하는 Outlook VSTO 추가 기능에 대해서만 필수 요소.|`Name`|  
|[&#60; m e &#62; 요소 &#40; Visual Studio &#41;에서 Office 개발](../vsto/vstoruntime-element-office-development-in-visual-studio.md)|필수 요소. Office 솔루션에서 지원되는 Visual Studio Tools for Office Runtime의 특정 버전을 설명합니다.|`release`<br /><br /> `version`<br /><br /> `supportUrl`|  
  
## <a name="remarks"></a>설명  
 Office 솔루션의 응용 프로그램 및 배포 매니페스트를 수동으로 편집할 수 있습니다. 나중에 매니페스트 생성 및 편집 도구(mage.exe 및 mageui.exe)를 사용하여 응용 프로그램 및 배포 매니페스트를 다시 서명해야 합니다. 자세한 내용은 [How to: Re-sign Application and Deployment Manifests](/visualstudio/deployment/how-to-re-sign-application-and-deployment-manifests)을 참조하세요.  
  
## <a name="file-location"></a>파일 위치  
 응용 프로그램 매니페스트는 솔루션의 단일 버전에 따라 다릅니다. 이러한 이유로 응용 프로그램 매니페스트를 배포 매니페스트와 분리하여 저장해야 합니다. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 는 버전별 파일을 게시 폴더의 **응용 프로그램 파일** 하위 디렉터리에 있는 관련 버전을 따라 명명된 하위 디렉터리에 배치합니다.  
  
## <a name="file-name-syntax"></a>파일 이름 구문  
 응용 프로그램 매니페스트 파일의 이름은 `assemblyIdentity` 요소에서 식별한 대로 응용 프로그램의 전체 이름 및 확장명(.manifest)이어야 합니다. 예를 들어 OutlookAddIn1.dll 사용자 지정을 참조하는 응용 프로그램 매니페스트는 다음 파일 이름 구문을 사용합니다.  
  
 `OutlookAddIn1.dll.manifest`  
  
## <a name="see-also"></a>참고 항목  
 [Office 솔루션에 대 한 배포 매니페스트](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce 응용 프로그램 매니페스트](/visualstudio/deployment/clickonce-application-manifest)  
  
  