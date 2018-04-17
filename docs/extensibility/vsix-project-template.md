---
title: VSIX 프로젝트 템플릿은 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- deploy packages
- publish extension
ms.assetid: b6c82167-e2a5-4cff-8c8b-2d72e2a9092c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: bff05b0b1b05a6b00b7924f0fb5bfc957adba41c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="vsix-project-template"></a>VSIX 프로젝트 템플릿
VSIX 프로젝트에서 하나 이상의 Visual Studio 확장을 래핑할 VSIX 프로젝트 템플릿을 사용 하 고 다음에 패키지를 게시할 수 있습니다는 [Visual Studio 갤러리](http://go.microsoft.com/fwlink/?LinkID=123847) 웹 사이트입니다.  
  
 VSIX 배포에는 Vspackage, 어셈블리, MEF 구성 요소, 프로젝트 템플릿, 항목 템플릿, 도구 상자 컨트롤 및 사용자 지정 확장 형식을 지원합니다.  
  
> [!NOTE]
>  VSIX 프로젝트를 사용 하려면 Visual Studio SDK를 설치 해야 합니다. Visual Studio SDK에 대 한 자세한 내용은 참조 [Visual Studio SDK](../extensibility/visual-studio-sdk.md)합니다.  
  
## <a name="where-to-find-the-vsix-project-template"></a>VSIX 프로젝트 템플릿을 찾을 수 있는 위치  
 VSIX 프로젝트 템플릿에에서 사용할 수는 **새 프로젝트** 대화 상자. 확장 된 **Visual Basic** 노드 또는 **Visual C#** 노드를 선택한 후 **확장성**합니다.  
  
> [!TIP]
>  있는지 확인 해야 해당.NET Framework 4.5 또는 이상이 맨 위에 있는 드롭다운 목록에 지정 된 된 **새 프로젝트** 대화 상자.  
  
## <a name="uses-of-the-vsix-project-template"></a>VSIX 프로젝트 템플릿 사용  
 VSIX 프로젝트 템플릿은 두 개의 주요 용도 있습니다.  
  
-   프로젝트 템플릿, 항목 템플릿 및 기타 확장을 VSIX 지원 아직 없으면를 배포 합니다.  
  
-   에 하나의 배포 패키지에 여러 개의 확장 프로그램의 출력을 래핑합니다.  
  
 VSIX 프로젝트 템플릿을 사용 하 여 Vspackage 또는 다른 종류의 지원 되는 VSIX를 이미 설치 된 확장을 배포할 필요가 없습니다.  
  
## <a name="packaging-an-extension-in-an-empty-vsix-project"></a>빈 VSIX 프로젝트에서 확장 패키지  
 기존 확장 또는 이미 사용 하 여 빈 VSIX 프로젝트에서 지원 되는 VSIX 없는 확장을 패키지할 수 있습니다. 확장을 래핑할 수에서 지원 되는 형식 이어야 합니다는 [VSIX 스키마](../extensibility/vsix-extension-schema-2-0-reference.md)합니다.  
  
#### <a name="to-package-an-extension-by-using-a-vsix-project"></a>VSIX 프로젝트를 사용 하 여 확장을 패키지 하려면  
  
1.  확장 프로그램을 구성 하는 프로젝트를 빌드하십시오.  
  
2.  사용 하 여 VSIX 프로젝트를 만들기는 **VSIX 프로젝트** 템플릿.  
  
     Source.extension.vsixmanifest 열립니다 **매니페스트 디자이너**합니다.  
  
3.  에 **자산** 탭, 선택는 **새로** 단추입니다.  
  
     **새 자산 추가** 대화 상자가 나타납니다.  
  
4.  에 **형식** 목록에서 추가할 확장의 유형을 선택 합니다.  
  
5.  현재 솔루션 (예: 항목 템플릿을 또는 컴파일된 어셈블리)에 포함 된 확장 프로그램이 나 콘텐츠 요소를 추가 하려면 다음 단계를 수행 합니다.  
  
    1.  에 **소스** 목록에서 선택 **현재 솔루션의 프로젝트**합니다.  
  
    2.  에 **프로젝트** 목록 확장의 이름을 선택 합니다.  
  
    3.  에 **이 폴더에 대 한 Embed** 상자 하 자산을 포함 하 고 다음을 선택 하는 폴더의 이름을 입력 합니다는 **확인** 단추입니다.  
  
6.  확장 또는 현재 솔루션에 포함 되지 않은 콘텐츠 요소를 추가 하려면 다음 단계를 수행 합니다.  
  
    1.  에 **소스** 목록 상자에서 선택 **파일 시스템의 파일**합니다.  
  
    2.  에 **경로** 필드 컴파일된 또는 압축 된 확장 파일에 전체 경로 입력 하거나 사용 하 여는 **찾아보기** 단추 하는 파일을 찾습니다.  
  
    3.  에 **이 폴더에 대 한 Embed** 상자 하 자산을 포함 하 고 다음을 선택 하는 폴더의 이름을 입력 합니다는 **확인** 단추입니다.  
  
7.  패키지의 추가 확장을 포함 하려는 경우 동일한 방식으로 추가 합니다.  
  
8.  솔루션을 빌드합니다.  
  
     [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] VSIX 매니페스트 파일, [Content_Types].xml 파일 및 프로젝트에 추가 하는 확장 자산을 모두 포함 하는.vsix 파일을 작성 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [VSIX 확장 2.0 스키마 참조](../extensibility/vsix-extension-schema-2-0-reference.md)   
 [Visual Studio 확장 찾기 및 사용](../ide/finding-and-using-visual-studio-extensions.md)