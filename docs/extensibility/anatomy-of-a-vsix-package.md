---
title: "VSIX 패키지 분석 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- visual studio extension
- vsix
- packages
ms.assetid: 8b86d62f-c274-4e91-82e0-38cdb9a423d5
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 519993c8527b0cd64c283416cd60eb48112e6886
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="anatomy-of-a-vsix-package"></a>VSIX 패키지 분석
VSIX 패키지는 메타 데이터를 분류 하 고 확장을 설치 하려면 Visual Studio에서는 하나 이상의 Visual Studio 확장을 포함 하는 파일입니다. VSIX 매니페스트 및 [Content_Types].xml 파일에 메타 데이터가 포함 되어 있습니다. VSIX 패키지 지역화 된 설치 프로그램 텍스트를 제공 하려면 하나 이상의 Extension.vsixlangpack 파일이 포함 될 수 있습니다 및 종속성을 설치 하려면 추가 VSIX 패키지를 포함할 수 있습니다.  
  
 VSIX 패키지 형식에는 개방형 패키징 규칙 (OPC) 표준을 따릅니다. 바이너리를 포함 하는 패키지와 매니페스트는.vsix 및 [Content_Types].xml 파일을 함께 지원 파일, 파일입니다. 한 VSIX 패키지는 여러 프로젝트 또는 자신의 매니페스트가 있는 여러 패키지의 출력을 포함할 수 있습니다.  
  
> [!NOTE]
>  VSIX 패키지에 포함 된 파일 이름은 공백을 포함 하지 않아야로 식별자 URI (Uniform Resource), 예약 된 문자 아래에 정의 된 또는 [ \[RFC2396\]](http://go.microsoft.com/fwlink/?LinkId=90339)합니다.  
  
## <a name="the-vsix-manifest"></a>VSIX 매니페스트  
 VSIX 매니페스트에 확장을 설치, 및 다음과 VSX 스키마에 대 한 정보를 포함 합니다. 자세한 내용은 참조 [VSIX 확장 스키마 1.0 참조](http://msdn.microsoft.com/en-us/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)합니다. VSIX 매니페스트 예제를 참조 하십시오. [PackageManifest 요소 (루트 요소, VSX 스키마)](http://msdn.microsoft.com/en-us/f8ae42ba-775a-4d2b-976a-f556e147f187)합니다.  
  
 VSIX 매니페스트에 명명 된 `extension.vsixmanifest` .vsix 파일에 포함 된 경우.  
  
## <a name="the-content"></a>콘텐츠  
 템플릿, 도구 상자 항목, Vspackage 또는 다른 종류의 Visual Studio에서 지원 되는 VSIX 패키지 포함할 수 있습니다.  
  
## <a name="language-packs"></a>언어 팩  
 VSIX 패키지는 한 번 또는 많은 Extension.vsixlangpack 파일 설치 중에 지역화 된 텍스트를 제공을 포함할 수 있습니다. 자세한 내용은 참조 [VSIX 패키지 지역화](../extensibility/localizing-vsix-packages.md)합니다.  
  
## <a name="dependencies-and-references"></a>종속성 및 참조  
 VSIX 패키지 다른 VSIX 패키지 참조를 포함할 수 있습니다. 각 다른 패키지는 자체 VSIX 매니페스트를 포함 해야 합니다.  
  
 사용자가 종속성이 포함 된 확장을 설치 하려고 하는 경우 설치 관리자에서 필요한 어셈블리 사용자 시스템에 설치 되어 있는지 확인 합니다. 필요한 어셈블리를 찾을 수 없는 경우 **확장명 및 업데이트** 누락 된 어셈블리의 목록을 표시 합니다.  
  
 확장 매니페스트에 하나 이상 포함 하는 경우 [참조](http://msdn.microsoft.com/en-us/32c52934-e81e-4b53-8cb6-4df45ef7bfa8) 요소 **확장명 및 업데이트** 시스템에 설치 된 확장에 대 한 각 참조의 매니페스트를 비교 하 고 설치는 아직 설치 되지 않은 경우 참조 된 확장명입니다. 이전 버전 참조 되는 확장의 설치 된 경우 최신 버전으로 대체 됩니다.  
  
 다중 프로젝트 솔루션의 프로젝트에 동일한 솔루션 있는 다른 프로젝트에 대 한 참조를 포함 하는 경우 해당 프로젝트의 종속성 VSIX 패키지에 포함 되어 있습니다. 내부 프로젝트에 대 한 한 다음에 대 한 참조를 클릭 하 여이 동작을 재정의할 수는 **속성** 설정 창에서 **출력 VSIX에 포함 된 그룹** 속성을 `BuiltProjectOutputGroup`합니다.  
  
 VSIX 패키지 위성 Dll에서 참조 된 어셈블리에 포함 하려면 추가 `SatelliteDllsProjectOutputGroup` 에 **출력 VSIX에 포함 된 그룹** 속성입니다.  
  
## <a name="installation-location"></a>설치 위치  
 설치 하는 동안 **확장명 및 업데이트** %LocalAppData%\Microsoft\VisualStudio\14.0\Extensions 아래의 폴더에는 VSIX 패키지 내용의 압축을 찾습니다.  
  
 기본적으로 설치 % LocalAppData % 사용자별 디렉터리 이므로 현재 사용자에만 적용 합니다. 그러나 설정 하는 경우는 [AllUsers](http://msdn.microsoft.com/en-us/ac817f50-3276-4ddb-b467-8bbb1432455b) 매니페스트를 요소의 `True`, 확장 프로그램에서 설치 됩니다... \\ *VisualStudioInstallationFolder*\Common7\IDE\Extensions 컴퓨터의 모든 사용자에 게 사용할 수 있습니다.  
  
## <a name="contenttypesxml"></a>[Content_Types].xml  
 [Content_Types].xml 파일에 확장 된.vsix 파일의 파일 형식을 식별합니다. Visual Studio 패키지를 설치 하는 동안이 파일을 사용 하지만 파일 자체를 설치 하지 않습니다. 이 파일에 대 한 자세한 내용은 참조 [[Content_types].xml 파일의 구조](the-structure-of-the-content-types-dot-xml-file.md)합니다.  
  
 [Content_Types].xml 파일에서 열기 패키징 규칙 (OPC) 표준 필요 합니다. OPC에 대 한 자세한 내용은 참조 [OPC: A 새 표준 데이터에 대 한 패키징 Your](http://go.microsoft.com/fwlink/?LinkID=148207) MSDN 웹 사이트에 있습니다.