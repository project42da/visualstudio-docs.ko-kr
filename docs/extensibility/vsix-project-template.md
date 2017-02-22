---
title: "VSIX 프로젝트 템플릿 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "패키지 배포"
  - "확장 게시"
ms.assetid: b6c82167-e2a5-4cff-8c8b-2d72e2a9092c
caps.latest.revision: 21
caps.handback.revision: 21
ms.author: "gregvanl"
manager: "ghogen"
---
# VSIX 프로젝트 템플릿
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

VSIX 프로젝트 템플릿을 사용 하 여 VSIX 프로젝트에서 하나 이상의 Visual Studio 확장을 배치 하 고 다음에 패키지를 게시할 수 있습니다는 [Visual Studio 갤러리](http://go.microsoft.com/fwlink/?LinkID=123847) 웹 사이트입니다.  
  
 VSIX 배포 Vspackage, 어셈블리, MEF 구성 요소, 프로젝트 템플릿, 항목 템플릿, 도구 상자 컨트롤 및 사용자 지정 확장 형식을 지원합니다.  
  
> [!NOTE]
>  VSIX 프로젝트를 사용 하려면 Visual Studio SDK를 설치 해야 합니다. Visual Studio SDK에 대 한 자세한 내용은 참조 [Visual Studio SDK](../extensibility/visual-studio-sdk.md)합니다.  
  
## VSIX 프로젝트 템플릿을 찾을 수 있는 위치  
 VSIX 프로젝트 템플릿에 사용할 수는 **새 프로젝트** 대화 상자입니다. 확장 하 고는 **Visual Basic** 노드 또는 **Visual C\#** 노드를 선택한 다음 **확장성**합니다.  
  
> [!TIP]
>  확인 해야 해당.NET Framework 4.5 또는 맨 위에 있는 드롭다운 목록에 지정 된 더 높은 **새 프로젝트** 대화 상자입니다.  
  
## VSIX 프로젝트 템플릿을 사용 하 여  
 VSIX 프로젝트 템플릿은 두 가지 주요 용도로 사용 합니다.  
  
-   프로젝트 템플릿, 항목 템플릿 및 다른 확장을 이미가 지원 되지 않으므로 VSIX를 배포 합니다.  
  
-   하나의 배포 패키지에 여러 확장의 출력을 래핑할 합니다.  
  
 VSIX 프로젝트 템플릿을 사용 하 여 Vspackage 또는 다른 종류의 확장 지원 VSIX에 이미 있는 배포할 필요가 없습니다.  
  
## 빈 VSIX 프로젝트에서 확장 패키지  
 기존 확장 또는 이미 사용 하 여 빈 VSIX 프로젝트에서 지원 되는 VSIX가 없는 확장을 패키징할 수 있습니다. 래핑될 확장에서 지원 되는 형식 이어야 합니다는 [VSIX 스키마](../extensibility/vsix-extension-schema-2-0-reference.md)합니다.  
  
#### VSIX 프로젝트를 사용 하 여 확장 프로그램을 패키지 하려면  
  
1.  확장 프로그램을 구성 하는 프로젝트를 빌드하십시오.  
  
2.  사용 하 여 VSIX 프로젝트를 만들기는 **VSIX 프로젝트** 템플릿.  
  
     Source.extension.vsixmanifest 열립니다 **매니페스트 디자이너**합니다.  
  
3.  에 **자산** 탭에서 선택은 **새로** 단추입니다.  
  
     **새 자산 추가** 대화 상자가 나타납니다.  
  
4.  에 **형식** 목록에서 추가할 확장의 유형을 선택 합니다.  
  
5.  현재 솔루션 \(예: 항목 템플릿 또는 컴파일된 어셈블리\)에 포함 된 확장 프로그램 또는 콘텐츠 요소를 추가 하려면 다음 단계를 수행 합니다.  
  
    1.  에 **소스** 목록에서 선택 **현재 솔루션의 프로젝트**합니다.  
  
    2.  에 **프로젝트** 목록 확장의 이름을 선택 합니다.  
  
    3.  에 **이 폴더에 포함** 상자 하, 자산을 포함 하 고 다음을 선택 하는 폴더의 이름을 입력 합니다는 **확인** 단추입니다.  
  
6.  확장명이 나 현재 솔루션에 포함 되지 않은 콘텐츠 요소를 추가 하려면 다음 단계를 수행 합니다.  
  
    1.  에 **소스** 목록 상자에서 선택 **파일 시스템의 파일**합니다.  
  
    2.  에 **경로** 필드 컴파일된 또는 압축 된 확장 파일에 전체 경로 입력 하거나 사용 하 여는 **찾아보기** 단추 하는 파일을 찾습니다.  
  
    3.  에 **이 폴더에 포함** 상자 하, 자산을 포함 하 고 다음을 선택 하는 폴더의 이름을 입력 합니다는 **확인** 단추입니다.  
  
7.  추가 확장을 포함 하도록 패키지를 하려는 경우 동일한 방식으로 추가 합니다.  
  
8.  솔루션을 빌드합니다.  
  
     [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] VSIX 매니페스트 파일, \[Content\_Types\].xml 파일 및 프로젝트에 추가 하는 확장 자산을 모두 포함 된.vsix 파일을 빌드합니다.  
  
## 참고 항목  
 [VSIX 확장 스키마 2.0 참조](../extensibility/vsix-extension-schema-2-0-reference.md)   
 [Visual Studio 확장 찾기 및 사용](../ide/finding-and-using-visual-studio-extensions.md)