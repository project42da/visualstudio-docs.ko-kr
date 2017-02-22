---
title: "VSIX 프로젝트 템플릿을 사용 하 여 시작 하기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "VSIX 프로젝트 템플릿 visual Studio SDK"
ms.assetid: 89fac33e-9380-4723-9b45-048a6e16f0ed
caps.latest.revision: 25
caps.handback.revision: 25
ms.author: "gregvanl"
manager: "ghogen"
---
# VSIX 프로젝트 템플릿을 사용 하 여 시작 하기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

확장 프로그램을 만들려면 또는 배포에 대 한 기존 확장 프로그램을 패키지 하려면 VSIX 프로젝트 템플릿을 사용할 수 있습니다. VSIX 프로젝트에는 Visual Basic 및 Visual C\# 버전, 템플릿과 Visual Studio SDK의 일부로 설치 됩니다.  
  
 VSIX 프로젝트 템플릿을만 구성 된 확장에 대 한 정보를 포함 하는 source.extension.vsixmanifest 파일 및 자산 제공 합니다.  
  
 VSIX 프로젝트 서식 파일을 찾으려면 Visual Studio SDK를 설치 해야 합니다. 자세한 내용은 [Visual Studio SDK](../extensibility/visual-studio-sdk.md)을 참조하십시오.  
  
## VSIX 프로젝트 템플릿을 사용 하 여 사용자 지정 프로젝트 템플릿 배포  
 다음 단계에는 VSIX 프로젝트를 Visual Studio 갤러리에 업로드 하거나 다른 개발자와 공유할 수 있는 프로젝트 템플릿을 패키지를 사용 하는 방법을 보여 줍니다.  
  
1.  프로젝트 템플릿을 만듭니다.  
  
    1.  서식 파일을 만드는 데 사용할 프로젝트를 엽니다. 이 프로젝트는 프로젝트 형식일 수 있습니다.  
  
    2.  **파일** 메뉴에서 **템플릿 내보내기**를 클릭합니다. 마법사의 단계를 완료 합니다.  
  
         %USERPROFILE%\\My Documents\\Visual Studio에서에서.zip 파일을 만들 *\< 버전 \>*\\My Exported Templates\\ 합니다.  
  
2.  빈 VSIX 프로젝트를 만듭니다.  
  
     **파일** 메뉴에서 **새로 만들기**를 클릭한 다음 **프로젝트**를 클릭합니다. 선택 **Visual Basic** 또는 **Visual C\#**합니다. 선택한 노드 아래의 **확장성**, 를 선택한 다음 **VSIX 프로젝트**합니다.  
  
3.  .Zip 파일을 프로젝트에 추가 합니다. 설정의 **출력 디렉터리로 복사** 속성을 `Copy Always`합니다.  
  
4.  에 **솔루션 탐색기**, 두 번 클릭 하는 `source.extension.vsixmanifest` 파일을 열에 **VSIX 매니페스트 디자이너**, 다음 다음과 같이 변경 하 고:  
  
    -   설정의 **제품 이름** 필드를 **내 프로젝트 템플릿을**합니다.  
  
    -   설정의 **제품 ID** 필드를 **MyProjectTemplate\-1**합니다.  
  
    -   설정의 **작성자** 필드를 **Fabrikam**합니다.  
  
    -   설정의 **설명** 필드를 **내 프로젝트 템플릿을**합니다.  
  
    -   에 **자산** 섹션을 추가 **Microsoft.VisualStudio.ProjectTemplate** 입력 하 고.zip 파일의 이름에 해당 경로 설정 합니다.  
  
5.  저장 하 고 source.extension.vsixmanifest 파일을 닫습니다.  
  
6.  프로젝트를 빌드합니다.  
  
7.  출력 디렉터리에서.vsix 파일을 두 번 클릭 합니다.  
  
8.  A **VSIX 설치 관리자** 메시지 상자가 나타납니다. 확장을 설치 하는 지침을 따릅니다.  
  
9. Visual Studio를 닫고 다시 엽니다.  
  
10. 선택 **확장 및 업데이트** \(에 **도구** 메뉴\)을 선택 하 고는 **템플릿** 범주입니다. 사용 가능한 확장 중 하나 여야 합니다 **내 프로젝트 템플릿을**합니다.  
  
11. 에 새 프로젝트 템플릿이 나타납니다는 **새 프로젝트** 원래 프로젝트 템플릿으로 같은 위치에 대화 상자입니다. 예를 들어, 라는 서식 파일을 만든 경우 **VB 콘솔** Visual Basic 콘솔 응용 프로그램에서 **VB 콘솔** Visual Basic로 동일한 창에 나타나는 **콘솔 응용 프로그램** 서식 파일입니다.  
  
#### 새 프로젝트 대화 상자에서 서식 파일의 위치를 지정 하려면  
  
1.  템플릿 폴더에는 *Visual Studio 설치 경로*\\Common7\\IDE\\ProjectTemplates 및 *Visual Studio 설치 경로*\\Common7\\IDE\\ItemTemplates 디렉터리입니다. 새 프로젝트 대화 상자에 있는 최상위 수준 섹션의 이름이 템플릿 폴더의 이름을 일치 정확 하 게 되지 않습니다. 그 차이점 템플릿 폴더의 이름을 사용 합니다.  
  
     .Vsix 파일 확장명을.zip으로 변경 하 고 파일을 엽니다.  
  
2.  서식 파일에 나타나야 하는 새 프로젝트 대화 상자의 특정 섹션으로 같은 이름의 새 폴더를 만듭니다.  
  
3.  서식 파일 하위 섹션에 나타나는 경우 동일한 이름의 하위 폴더를 만듭니다.  
  
4.  템플릿.zip 파일을 새 폴더로 이동 합니다.  
  
5.  .Vsix를.zip 확장명을 변경 합니다.  
  
6.  VSIX 매니페스트를 엽니다.  
  
7.  VSIX 매니페스트를 업데이트는 **자산** 한다는 템플릿 파일을 포함 하는 디렉터리 트리의 루트를 가리키는 있도록 서식 파일의 경로입니다. 예를 들어 템플릿을 \\CSharp\\Windows에 있으면 참조 \\CSharp를 가리켜야 합니다.