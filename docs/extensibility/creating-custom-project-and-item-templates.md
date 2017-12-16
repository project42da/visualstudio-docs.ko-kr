---
title: "사용자 지정 프로젝트 및 항목 템플릿 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 586da5dc-f678-402b-afd0-0332959fd7a6
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b3081537b1704fd461a458798d646bf7eeb65f0a
ms.sourcegitcommit: f36eb7f989efbdbed0d0a087afea8ffe27d8ca15
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/14/2017
---
# <a name="creating-custom-project-and-item-templates"></a>사용자 지정 프로젝트 및 항목 템플릿 만들기
Visual Studio SDK에는 사용자 지정 프로젝트 템플릿 및 사용자 지정 항목 템플릿 만들기 있는 프로젝트 템플릿이 포함 되어 있습니다. 이러한 템플릿은 몇 가지 일반적인 매개 변수 대체 단어를 포함 하 고 zip 파일로 빌드합니다. 자동으로 배포 되지, 및 실험적 인스턴스에서 사용할 수 없는 경우. Zip을 복사 해야 위치에 파일  
  
 서식 파일 만들기 서식 파일을 통해 더 큰 확장 프로그램에 템플릿을 포함할 수 있도록 합니다. 이렇게 하면 소스 파일에 버전 제어를 구현 하 고 서식 파일 프로젝트 그룹을 하나의 VSIX 패키지로 빌드합니다.  
  
 사용 해야 기본 템플릿 만들기 시나리오는 **템플릿 내보내기** 압축된 파일에 출력 하는 마법사입니다. 기본 템플릿 만드는 방법에 대 한 자세한 내용은 참조 [프로젝트 만들기 및 항목 템플릿](../ide/creating-project-and-item-templates.md)합니다.  
  
 Visual Studio 2017 년부터 사용자 지정 프로젝트 및 항목 템플릿 검색 더 이상 수행 됩니다. 대신, 확장 이러한 서식 파일의 설치 위치를 설명 하는 템플릿 매니페스트 파일을 제공 해야 합니다. VSIX 확장을 업데이트 하려면 Visual Studio 2017을 사용할 수 있습니다. MSI를 사용 하 여 확장 프로그램을 배포 하는 경우 템플릿 매니페스트 파일을 직접 생성 해야 합니다. 자세한 내용은 참조 [사용자 지정 프로젝트 업그레이드 및 Visual Studio 2017에 대 한 항목 템플릿](../extensibility/upgrading-custom-project-and-item-templates-for-visual-studio-2017.md)합니다. 템플릿 매니페스트 스키마에 설명 되어 [Visual Studio 템플릿 매니페스트 스키마 참조](../extensibility/visual-studio-template-manifest-schema-reference.md)합니다.  
  
## <a name="creating-a-project-template"></a>프로젝트 템플릿 만들기  
  
1.  프로젝트 템플릿 프로젝트를 만듭니다. 프로젝트 템플릿을 찾을 수 있습니다는 **새 프로젝트** 대화 상자에서 Visual Basic 또는 Visual C#에서 **확장성** 폴더입니다.  
  
     클래스 파일, 아이콘,.vstemplate 파일, 명명 된 ProjectTemplate.vbproj 또는 ProjectTemplate.csproj, 한 편집 가능한 프로젝트 파일 및 일반적으로 다른 프로젝트 형식에 이러한 resources.resx 파일, 한 어셈블리 정보에서 생성 되는 일부 파일을 생성 하는 서식 파일 파일 및.settings 파일입니다. 적절 한 공통 매개 변수 대체를 포함 하는 각 코드 파일.  
  
2.  추가 하 고 프로젝트에 대해 필요에 따라 프로젝트에서 항목을 제거 합니다. 편집 가능한 프로젝트 파일, AssemblyInfo 파일 또는.vstemplate 파일을 제거 하지 마십시오.  
  
3.  모든 추가 삭제를 반영 하도록.vstemplate 파일을 업데이트 합니다. [프로젝트](../extensibility/project-element-visual-studio-templates.md) 요소를 포함 해야는 [ProjectItem](../extensibility/projectitem-element-visual-studio-item-templates.md) 서식 파일에 포함할 각 파일에 대 한 요소입니다.  
  
4.  코드 파일 및 기타 사용자 용 콘텐츠를 수정 하 고 적절 한 매개 변수 대체를 추가 합니다.  
  
5.  필요에 따라 생성된 된 콘텐츠를 수정 합니다.  
  
6.  프로젝트를 빌드합니다.  
  
     Visual Studio 템플릿이 포함 된.zip 파일을 만듭니다. 배포 되지 않은 하 고 실험적 인스턴스에서 사용할 수 있습니다.  
  
## <a name="creating-an-item-template"></a>항목 템플릿 만들기  
  
1.  항목 템플릿을 프로젝트를 만듭니다.  
  
     템플릿은 클래스 파일, 아이콘,.vstemplate 파일 및 어셈블리 정보 파일을 생성합니다. 클래스 파일에는 몇 가지 일반적인 매개 변수 대체 포함 되어 있습니다.  
  
2.  추가 하 고 프로젝트에 대해 필요에 따라 프로젝트에서 항목을 제거 합니다.  
  
3.  모든 추가 삭제를 반영 하도록.vstemplate 파일을 업데이트 합니다. [프로젝트](../extensibility/project-element-visual-studio-templates.md) 요소를 포함 해야는 [ProjectItem](../extensibility/projectitem-element-visual-studio-item-templates.md) 서식 파일에 포함할 각 파일에 대 한 요소입니다.  
  
4.  코드 파일 및 기타 사용자 용 콘텐츠를 수정 하 고 적절 한 매개 변수 대체를 추가 합니다.  
  
5.  필요에 따라 생성 된 콘텐츠를 수정 합니다.  
  
6.  프로젝트를 빌드합니다.  
  
     Visual Studio 템플릿이 포함 된 압축된 파일을 만듭니다. 배포 되지 않은 하 고 실험적 인스턴스에서 사용할 수 있습니다.  
  
## <a name="deployment"></a>배포  
  
#### <a name="to-deploy-the-project-or-item-template"></a>프로젝트 또는 항목 템플릿 배포 하려면  
  
1.  VSIX 프로젝트를 만듭니다. 자세한 내용은 참조 [VSIX 프로젝트 템플릿은](../extensibility/vsix-project-template.md)합니다.  
  
2.  VSIX 프로젝트를 시작 프로젝트로 설정 합니다. 에 **솔루션 탐색기**, VSIX 프로젝트 노드를 마우스 오른쪽 단추로 클릭 및 선택 선택 **시작 프로젝트로 설정**합니다.  
  
3.  VSIX 프로젝트의 자산으로 프로젝트 템플릿 프로젝트를 설정 합니다. .Vsixmanifest 파일을 엽니다. 이동 하 여 **자산** 탭을 클릭 **새로**합니다.  
  
    1.  설정의 **형식** 필드를 **Microsoft.VisualStudio.ProjectTemplate** 또는 **Microsoft.VisualStudio.ItemTemplate**합니다.  
  
    2.  원본에 대 한 선택은 **현재 솔루션의 프로젝트** 옵션을 선택한 다음 템플릿이 포함 된 프로젝트를 선택 합니다.  
  
4.  솔루션을 작성 하 고 F5 키를 누릅니다. 실험적 인스턴스가 표시 됩니다.  
  
5.  프로젝트 템플릿 프로젝트에 나열 된 프로젝트 템플릿이 표시 됩니다는 **새 프로젝트** 대화 (**파일 > 새로 만들기 > 프로젝트**), Visual C# 또는 Visual Basic 노드. 서식 파일 프로젝트 항목에 대 한 새 항목 추가 대화 상자에 나열 된 항목 템플릿을 표시 됩니다 (에 **솔루션 탐색기**프로젝트 노드를 선택 하 고 클릭 **추가 / 새 항목**).  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio 템플릿 참조](../ide/visual-studio-template-reference.md)