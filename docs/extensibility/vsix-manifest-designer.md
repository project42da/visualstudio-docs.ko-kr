---
title: "VSIX 매니페스트 디자이너 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.Sdk.VsixManifestEditor
helpviewer_keywords:
- vsixmanifest
- vsix manifest
- manifest designer
ms.assetid: 5a691e77-cf91-430d-90ea-361d9031ef83
caps.latest.revision: "20"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 0d7af3ab109c922a8182a93db6852a331229ceca
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="vsix-manifest-designer"></a>VSIX 매니페스트 디자이너
VSIX 패키지 매니페스트 파일을 설정 하는 Visual Studio 확장에 대 한 설치 동작을 수정 합니다.  
  
 **VSIX 매니페스트 디자이너** 기본 VSIX 스키마에 매핑됩니다. 디자이너에서 해당 컨트롤을 사용 하 여 스키마의 모든 요소를 설정할 수 있습니다. 스키마에 대 한 자세한 내용은 참조 [VSIX 확장 스키마 2.0 참조](../extensibility/vsix-extension-schema-2-0-reference.md)합니다.  
  
 열려는 **VSIX 매니페스트 디자이너**, source.extension.vsixmanifest 파일을 찾고 **솔루션 탐색기**, 파일을 엽니다. 파일에 유효한 XML이 없는 경우에 매니페스트 디자이너 열리지 않습니다.  
  
> [!NOTE]
>  Source.extension.vsixmanifest은 패키지를 빌드할 때 extension.vsixmanifest 출력 합니다.  
  
## <a name="uielement-list"></a>UI 요소 목록  
 **VSIX 매니페스트 디자이너** 스키마의 최상위 이러한 요소에 해당 하는 4 개의 섹션이 포함 되어 있습니다.  
  
-   메타데이터  
  
-   설치 대상  
  
-   자산  
  
-   종속성  
  
 제목 영역에는 다음과 같은 컨트롤이 들어 있습니다.  
  
 **제품 이름**  
 확장 이름에 설명합니다.  
  
 **제품 ID**  
 이 패키지에 대 한 고유 식별 정보를 지정합니다.  
  
 **작성자**  
 확장 프로그램의 작성자의 이름을 지정합니다.  
  
 **Version**  
 확장의 버전 번호를 지정합니다.  
  
 **메타 데이터** 탭에는 다음과 같은 컨트롤입니다.  
  
 **설명**  
 에 표시 되는 확장에 대 한 텍스트 설명을 제공 **확장 관리자**합니다.  
  
 **언어**  
 매니페스트에 텍스트 데이터에 해당 하는 패키지에 대 한 기본 언어를 지정 합니다. `Language` 특성 en 예를 들어 리소스 어셈블리에 대 한 공용 언어 런타임 (CLR) 로캘 코드 규칙을 따르는-우리, en, fr-fr 합니다. 기본적으로 값은 중립; 즉, 모든 언어 버전의 Visual Studio에서 패키지를 실행 합니다.  
  
 **라이선스**  
 이 있는 경우 사용자 라이선스를 포함 하는 텍스트 파일을 지정 합니다.  
  
 **아이콘**  
 에 표시할 아이콘을 포함 하는 그래픽 파일 (.png,.bmp,.jpeg,.ico)을 지정 **확장 관리자**는 아이콘이 표시 되 면, 합니다. 아이콘 이미지는 32 x 32 픽셀 이어야 합니다. 또는 해당 차원에 크기가 조정 됩니다. 아이콘이 없는 지정 된 경우 **확장 관리자** 기본 아이콘을 사용 합니다.  
  
 **미리 보기 이미지**  
 에 표시할 미리 보기 이미지를 포함 하는 그래픽 파일 (.png,.bmp,.jpeg,.ico)을 지정 **확장 관리자**미리 보기 이미지가 있는 경우, 합니다. 미리 보기 이미지에는 200 x 200 픽셀 이어야 합니다. 미리 보기 이미지가 지정 된 경우 **확장 관리자** 기본 이미지를 사용 합니다.  
  
 **태그**  
 검색 힌트에 사용할 텍스트 태그를 추가 합니다.  
  
 **릴리스 정보**  
 릴리스 정보를 포함 하는 파일 (.txt,.rtf)을 지정 합니다. 또한 릴리스 정보를 표시 하는 웹 사이트의 URL을 사용 합니다.  
  
 **시작 가이드**  
 VSIX 패키지의 확장 또는 콘텐츠를 사용 하는 방법에 대 한 정보를 포함 하는 파일 (.txt,.rtf)을 지정 합니다. 이 가이드에는 확장 설치가 완료 되 면 표시 됩니다. 또한이 가이드를 표시 하는 웹 사이트의 URL을 사용 합니다.  
  
 **자세한 정보 URL**  
 제품에 대 한 추가 정보를 포함 하는 웹 사이트의 URL을 지정 합니다.  
  
 **설치 대상** 탭에는 다음과 같은 컨트롤입니다.  
  
 **설치 유형**  
 나열 **Visual Studio Extension** 및 **확장명 SDK를 사용한** 설치 형식을 대상으로 합니다. 옵션 선택 하는 유형에 따라 다릅니다.  
  
 **Visual Studio 확장**  
 나열 된 **InstallationTarget** 요소를 설명 하는 방법을 패키지를 설치할 수 있는 Visual Studio 제품에이 확장을 설치할 수 있습니다. 각 제품 이름 및 버전 또는 버전 범위 내에서 개별적으로 식별 됩니다.  제품 목록에 추가, 수정 및 삭제 될 수 있습니다. 이름 및 제품의 버전에 해당 하는 **Id** 및 **버전** 는 연관 된 특성 **InstallationTarget** 요소입니다.  
  
 **버전 범위** 은 [12.0, 14.0] 다음과 같이 출력을 사용 하 여:  
  
-   [-최소 버전 (포함)  
  
-   ]-최대 버전 (포함)  
  
-   (-단독 최소 버전  
  
-   )-최대 버전 전용  
  
-   단일 버전 #-지정된 된 버전만  
  
 **확장 SDK**  
 특정 제품 및 버전으로 한정 되지 않습니다 전역 설치를 지정 합니다. **대상 플랫폼 식별자** 예: "Windows" 대상으로 하는 플랫폼입니다. **대상 플랫폼 버전** 같은 8.0 대상 플랫폼의 버전입니다. **SDK 이름이 며** 및 **SDK 버전** 이름과 SDK의 버전 번호는 각각.  
  
 **이 VSIX가 모든 사용자 용 으로만 설치 (설치 시 권한을 높여야 함)** 확인란  
 모든 사용자를 위한이 확장이 설치 되어이 확인란을 선택 하는 경우 그렇지 않으면 현재 사용자에 대해서만 설치 됩니다.  
  
 **이 VSIX는 Windows Installer 설치** 확인란  
 Windows Installer (.msi 파일);에서이 확장 프로그램이 설치 되어이 확인란을 선택 하는 경우 그렇지 않으면 일반적인 VSIX 패키지 (.vsix 파일)으로 설치 됩니다.  
  
 **자산** 탭에는 다음과 같은 컨트롤입니다.  
  
 **자산 목록**  
 확장 또는 콘텐츠 요소에 설명 하는 자산 요소를 나열이 패키지 화면을 표시 합니다. 각 확장 프로그램이 나 콘텐츠 요소는 원본, 유형 및 경로로 별도로 나열 됩니다. 확장명 및 콘텐츠 요소는 목록에 추가, 수정 및 삭제 될 수 있습니다. 유형 및 확장 또는 콘텐츠 요소의 경로에 해당 하는 `Type` 및 `Path` 는 연관 된 특성 `Asset` 요소입니다. 다음과 같은 알려진 있습니다.  
  
-   Microsoft.VisualStudio.Package  
  
-   Microsoft.VisualStudio.MefComponent  
  
-   Microsoft.VisualStudio.ToolboxControl  
  
-   Microsoft.VisualStudio.Samples  
  
-   Microsoft.VisualStudio.ProjectTemplate  
  
-   Microsoft.VisualStudio.ItemTemplate  
  
-   Microsoft.VisualStudio.Assembly  
  
-   Microsoft.ExtensionSDK  
  
 를 추가 하거나 자산을 편집 하려면 자산 프로젝트의 이름 및 파일 시스템에 현재 솔루션에 프로젝트 또는 파일 인지 여부를 자산 형식을 지정 해야 합니다. 또한를 포함할 수 있는 폴더의 이름을 지정할 수 있습니다.  
  
 또한 사용자 고유의 형식을 만들고 고유한 이름을 지정 수 있습니다.  
  
 **종속성** 탭에는 다음과 같은 컨트롤입니다.  
  
 **이름, 원본 및 버전 범위**  
 이 패키지에 종속 된 다른 패키지는이 패키지의 종속 요소를 나열 합니다. 종속성 패키지를 지정 하는 경우 설치 해야이 패키지를 설치 하 고; 하기 전에 그렇지 않은 경우이 패키지 설치 해야 합니다.  
  
 종속성 패키지 식별자, 이름, 버전 범위, 소스 및 종속성 해결 되어야 하는 방법으로 지정 됩니다. 각 종속성 패키지 이름, 버전 및 소스에서 별도로 나열 됩니다. 종속성 패키지 목록에 추가, 수정 및 삭제 수 수 있습니다.  
  
 식별자와 일치 해야 합니다는 `ID` 종속성 패키지 메타 데이터의 특성입니다. 원본은 현재 솔루션, 현재 설치 된 확장명 또는 파일에서 프로젝트를 수 있습니다. **종속성 확인 방법은** 중첩 된 패키지의 상대 경로 또는 URL 종속성에 대 한 다운로드 위치를 설정할 수 있습니다. 에 해당 하는 ID, 버전 및 종속성 패키지의 해상도 `Id`, `Version`, 및 `Location` 는 연관 된 특성 `Dependency` 요소입니다.  
  
## <a name="see-also"></a>참고 항목  
 [VSIX 확장 2.0 스키마 참조](../extensibility/vsix-extension-schema-2-0-reference.md)   
 [VSIX 패키지 분석](../extensibility/anatomy-of-a-vsix-package.md)