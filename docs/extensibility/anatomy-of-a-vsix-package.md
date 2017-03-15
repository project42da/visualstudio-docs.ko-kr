---
title: "VSIX 패키지에 대 한 분석 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- visual studio extension
- vsix
- packages
ms.assetid: 8b86d62f-c274-4e91-82e0-38cdb9a423d5
caps.latest.revision: 15
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 7278fb37984b92a6a07823c552db5c59a446d0d2
ms.openlocfilehash: 633db03670180ac83c5c936f66953fb38d4ebd67
ms.lasthandoff: 02/22/2017

---
# <a name="anatomy-of-a-vsix-package"></a>VSIX 패키지에 대 한 분석
VSIX 패키지는 하나 이상의 Visual Studio 확장 Visual Studio 확장을 설치 하 고 분류를 사용 하 여 메타 데이터를 포함 하는 파일입니다. 해당 메타 데이터는 VSIX 매니페스트 및 [Content_Types].xml 파일에 포함 됩니다. VSIX 패키지 지역화 된 설치 프로그램 텍스트를 제공 하려면 하나 이상의 Extension.vsixlangpack 파일에 포함 될 수도 있습니다 및 종속성을 설치 하려면 추가 VSIX 패키지에 포함 될 수 있습니다.  
  
 VSIX 패키지 형식 규칙 OPC (Open Packaging) 표준을 따릅니다. 바이너리를 포함 하는 패키지와 매니페스트 함께 [Content_Types].xml 파일 및.vsix 파일을 지 원하는 파일. 하나의 VSIX 패키지는 여러 프로젝트 또는 자신의 매니페스트에 있는 여러 패키지의 출력을 포함할 수 있습니다.  
  
> [!NOTE]
>  VSIX 패키지에 포함 된 파일의 이름은 공백을 포함할 수 없습니다도로 식별자 URI (Uniform Resource), 예약 된 문자 아래에 정의 된 [ \[r f c&2396;\]](http://go.microsoft.com/fwlink/?LinkId=90339)합니다.  
  
## <a name="the-vsix-manifest"></a>VSIX 매니페스트  
 VSIX 매니페스트를 사용 하면 설치할 확장 및 다음과 VSX 스키마에 대 한 정보가 있습니다. 자세한 내용은 참조 [VSIX 확장 스키마 1.0 참조](http://msdn.microsoft.com/en-us/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)합니다. VSIX 매니페스트 예제를 참조 하십시오. [PackageManifest 요소 (루트 요소, VSX 스키마)](http://msdn.microsoft.com/en-us/f8ae42ba-775a-4d2b-976a-f556e147f187)합니다.  
  
 VSIX 매니페스트 이름으로 지정 되어야 `extension.vsixmanifest` .vsix 파일에 포함 됩니다.  
  
## <a name="the-content"></a>콘텐츠  
 VSIX 패키지 템플릿, 도구 상자 항목, Vspackage, 또는 다른 종류의 Visual Studio에서 지원 되는 확장에 포함 될 수 있습니다.  
  
## <a name="language-packs"></a>언어 팩  
 VSIX 패키지는 한 번 또는 설치 하는 동안 지역화 된 텍스트를 제공 하는 더 많은 Extension.vsixlangpack 파일에 포함할 수 있습니다. 자세한 내용은 참조 [VSIX 패키지 지역화](../extensibility/localizing-vsix-packages.md)합니다.  
  
## <a name="dependencies-and-references"></a>종속성 및 참조  
 VSIX 패키지 다른 VSIX 패키지 참조를 포함할 수 있습니다. 이러한 다른 패키지의 각 자체 VSIX 매니페스트를 포함 해야 합니다.  
  
 사용자가 확장에 종속성을 설치 하려고 하는 경우 설치 관리자는 필요한 어셈블리 사용자 시스템에 설치 되어 있는지 확인 합니다. 필요한 어셈블리를 찾을 수 없는 경우 **확장 및 업데이트** 누락 된 어셈블리의 목록이 표시 됩니다.  
  
 하나 이상의 확장 매니페스트에 포함 되어 있는 경우 [참조](http://msdn.microsoft.com/en-us/32c52934-e81e-4b53-8cb6-4df45ef7bfa8) 요소 **확장 및 업데이트** 시스템에 설치 된 확장에 대 한 각 참조의 매니페스트를 비교 하 고 아직 설치 되지 않은 경우 참조 되는 확장을 설치 합니다. 이전 버전에 참조 되는 확장의 설치 된 경우 최신 버전으로 대체 됩니다.  
  
 다중 프로젝트 솔루션에서 프로젝트를 동일한 솔루션에 다른 프로젝트에 대 한 참조를 포함 하는 경우 해당 프로젝트의 종속성 VSIX 패키지에 포함 되어 있습니다. 내부 프로젝트를 선택한 다음에 대 한 참조를 클릭 하 여이 동작을 재정의할 수는 **속성** 설정 창에서 **출력 VSIX에 포함 된 그룹** 속성을 `BuiltProjectOutputGroup`합니다.  
  
 VSIX 패키지에 참조 된 어셈블리의 위성 Dll을 포함 하려면 추가 `SatelliteDllsProjectOutputGroup` 에 **출력 VSIX에 포함 된 그룹** 속성입니다.  
  
## <a name="installation-location"></a>설치 위치  
 설치 하는 동안 **확장 및 업데이트** %LocalAppData%\Microsoft\VisualStudio\14.0\Extensions 하위 폴더에 VSIX 패키지의 콘텐츠를 찾습니다.  
  
 기본적으로 설치 % LocalAppData %는 사용자 고유의 디렉터리 때문에 현재 사용자에만 적용 합니다. 그러나 설정 하는 경우는 [AllUsers](http://msdn.microsoft.com/en-us/ac817f50-3276-4ddb-b467-8bbb1432455b) 요소에는 매니페스트의 `True`, 확장 프로그램에서 설치 됩니다... \\ *VisualStudioInstallationFolder*\Common7\IDE\Extensions 컴퓨터의 모든 사용자에 게 사용할 수 있습니다.  
  
## <a name="contenttypesxml"></a>[Content_Types].xml  
 [Content_Types].xml 파일에는 확장 된.vsix 파일에서 파일 형식을 식별합니다. Visual Studio 패키지를 설치 하는 동안이 파일을 사용 하지만 자체 파일을 설치 하지 않습니다. 이 파일에 대 한 자세한 내용은 참조 [[Content_types].xml 파일의 구조](the-structure-of-the-content-types-dot-xml-file.md)합니다.  
  
 [Content_Types].xml 파일을 여는 규칙 OPC (Open Packaging) 표준 필요 합니다. OPC에 대 한 자세한 내용은 참조 [OPC: A 새 표준 데이터에 대 한 패키징 Your](http://go.microsoft.com/fwlink/?LinkID=148207) MSDN 웹 사이트의.
