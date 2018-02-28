---
title: "언어 서비스 및 편집기 확장 시작 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], new - extensions
ms.assetid: 6b151891-c06d-40b1-9867-42298caa8492
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 5f7b7440ff2f42eba1d138872071d4e51d2402c1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="getting-started-with-language-service-and-editor-extensions"></a>언어 서비스 및 편집기 확장 시작
언어 서비스 기능 개요, 중괄호 일치, IntelliSense, 전구 등 선택한 프로그래밍 언어에 어떤 콘텐츠 형식 추가 하려면 편집기 확장을 사용할 수 있습니다. 모양 및 동작의 예를 들어 텍스트 색 지정, 여백, 장식, 및 기타 시각적 요소 Visual Studio 편집기에서 사용자 지정할 수도 있습니다. 사용자 고유의 유형의 콘텐츠를 정의 하 고 모양 및 동작 콘텐츠에 표시 되는 텍스트 뷰를 지정할 수도 있습니다.  
  
 편집기 확장을 쓸 시작 하려면 Visual Studio SDK의 일부로 설치 되어 있는 편집기 프로젝트 템플릿을 사용 합니다. Visual Studio SDK는 다운로드 가능한 도구 집합을 보다 쉽게 Vspackage를 사용 하 여 또는 프레임 워크 MEF (Managed Extensibility)를 사용 하 여 Visual Studio 확장 프로그램을 개발할 수 있도록 합니다.  
  
> [!NOTE]
>  Visual Studio SDK에 대 한 자세한 내용은 참조 [Visual Studio SDK](../extensibility/visual-studio-sdk.md)합니다.  
  
 사용자 고유의 편집기 확장을 작성 하기 전에 다음과 같은 개념 및 기술에 대 한 자세한 하는 것이 좋습니다.  
  
## <a name="the-windows-presentation-foundation-wpf-and-editor-extensions"></a>Windows Presentation Foundation (WPF) 및 편집기 확장  
 Visual Studio 편집기 사용자 인터페이스 (UI) (WPF (Windows Presentation Foundation)를 사용 하 여 구현 됩니다. WPF는 비즈니스 논리에서 코드의 시각적 측면을 구분 하는 일관 된 프로그래밍 모델 및 풍부한 시각적 효과 제공 합니다. 편집기 확장을 만들 때 다양 한 WPF 요소와 기능을 사용할 수 있습니다. 자세한 내용은 참조 [Windows Presentation Foundation](/dotnet/framework/wpf/index)합니다.  
  
## <a name="the-managed-extensibility-framework-mef-and-editor-extensions"></a>Managed Extensibility Framework (MEF) 및 편집기 확장  
 Visual Studio 편집기는 프레임 워크 MEF (Managed Extensibility)를 사용 하 여 해당 구성 요소 및 확장을 관리 합니다. MEF에는 또한 개발자를 자세한 Visual Studio와 같은 호스트 응용 프로그램에 대 한 확장을 쉽게 만들 수 있습니다. 이 프레임 워크는 MEF 계약에 따라 확장을 정의 하 고 MEF 구성 요소 부분으로 내보내기. 호스트 응용 프로그램을 찾아서, 등록, 올바른 컨텍스트에 적용 되는 선택 되어 있는지 확인 하는 구성 요소 부분을 관리 합니다.  
  
> [!NOTE]
>  편집기에서 MEF에 대 한 자세한 내용은 참조 [편집기에서 Managed Extensibility Framework](../extensibility/managed-extensibility-framework-in-the-editor.md)합니다.  
  
## <a name="visual-studio-editor-extension-points-and-extensions"></a>Visual Studio 편집기 확장 지점 및 확장  
 편집기 확장 사항이 MEF 구성 요소 부분을 사용자 지정 하 고 확장할 수 있는 합니다. 일부 경우에 올바른 메타 데이터 내보내기 및 인터페이스를 구현 하 여 확장 지점을 확장 합니다. 다른 경우에만 선언 하 확장 고 특정 형식으로 내보냅니다.  
  
 다음은 몇 가지 기본적인 종류의 편집기 확장입니다.  
  
-   여백 및 스크롤 막대  
  
-   Tags  
  
-   장식  
  
-   옵션  
  
-   IntelliSense  
  
 편집기 확장 지점에 대 한 자세한 내용은 참조 [언어 서비스 및 편집기 확장 지점](../extensibility/language-service-and-editor-extension-points.md)합니다.  
  
## <a name="deploying-editor-extensions"></a>편집기 확장 배포  
 Visual Studio에서 솔루션을 빌드할 솔루션에 source.extension.vsixmanifest 라는 메타 데이터 파일을 추가 하 고 다음 Visual Studio에 알려져 있는 폴더에 이진 파일 및 매니페스트의 복사본을 추가 하 여 편집기 확장을 배포 합니다. 매니페스트 파일 (예를 들어, 이름, 작성자, 버전 및 유형의 콘텐츠) 확장에 대 한 기본적인 사항을 정의합니다. VSIX 매니페스트 파일 및 확장을 배포 하는 방법에 대 한 자세한 내용은 참조 [Visual Studio 확장명 전달](../extensibility/shipping-visual-studio-extensions.md)합니다.  
  
 컴퓨터에 확장을 설치할 때 Visual Studio로 알려져 있는 폴더의 하위 폴더에 이진 파일 및 매니페스트를 포함 합니다.  
  
> [!WARNING]
>  Visual Studio에 포함 된 편집기 확장성 템플릿 중 하나를 사용 하는 경우 매니페스트 및 배포 위치에 대 한 세부 정보에 걱정할 필요가 없습니다. 템플릿을 등록 하 고 확장 배포 하는 데 필요한 정보가 모두 들어 있습니다.  
  
## <a name="running-extensions-in-the-experimental-instance"></a>실험적 인스턴스에서 실행 중인 확장  
 (Windows Vista 및 Windows 7)에서 다음 실험 폴더에 배포 하 여 확장을 개발 하는 동안 Visual Studio 작업 버전을 분리 수 있습니다.:  
  
 *% LOCALAPPDATA %*\VisualStudio\10.0Exp\Extensions\\*회사*\\*확장 Id*  
  
 여기서 *% LOCALAPPDATA %* 로그온 한 사용자의 이름인 *회사* 확장명을 소유 하는 회사의 이름 및 *확장 Id* 확장의 ID입니다.  
  
 실험적 위치에 확장을 배포할 때 디버그 모드에서 실행 됩니다. Visual Studio의 두 번째 인스턴스가 시작 되 고 라는 **Microsoft Visual Studio 실험적 인스턴스**합니다.  
  
## <a name="managing-extensions"></a>확장 관리  
 Visual studio 확장에 나열 됩니다 **확장명 및 업데이트** (에 **도구** 메뉴). 실험적 인스턴스에서 확장을 테스트 하는 경우에 표시 됩니다 **확장명 및 업데이트** 실험적 인스턴스에서 하지만 개발 인스턴스에 나타나지 않습니다.  
  
 자세한 내용은 [Visual Studio 확장명 찾기 및 사용](../ide/finding-and-using-visual-studio-extensions.md)을 참조하세요.  
  
## <a name="using-templates-to-create-editor-extensions"></a>편집기 확장을 만드는 템플릿을 사용 하 여  
 분류자, 장식 및 여백을 사용자 지정 하는 MEF 확장을 만드는 편집기 서식 파일을 사용할 수 있습니다. C# 및 Visual Basic 프로젝트에 대 한 템플릿이 있습니다. 자세한 내용은 참조 [편집기 항목 템플릿을 사용 하 여 확장을 만드는](../extensibility/creating-an-extension-with-an-editor-item-template.md)합니다.  
  
 또한 확장을 만드는 VSIX 프로젝트 템플릿을 사용할 수 있습니다. 이 템플릿은 모든 종류의 확장을 배포 하 고 source.extension.vsixmanifest 파일, 필요한 어셈블리 참조 및 배포할 수 있도록 하는 빌드 작업을 포함 하는 프로젝트 파일을 포함 하는 데 필요한 요소에만 제공는 확장입니다. 자세한 내용은 참조 [VSIX 프로젝트 템플릿은](../extensibility/vsix-project-template.md)합니다.  
  
 작업을 Visual Studio 패키지 확장 프로그램에서 MEF 구성 요소 편집기도 만들 수도 있습니다. 자세한 내용은 다음 연습을 참조 합니다.  
  
-   [연습: 편집기 확장에서 셸 명령 사용](../extensibility/walkthrough-using-a-shell-command-with-an-editor-extension.md)  
  
-   [연습: 편집기 확장에서 바로 가기 키 사용](../extensibility/walkthrough-using-a-shortcut-key-with-an-editor-extension.md)  
  
## <a name="see-also"></a>참고 항목  
 [언어 서비스 및 편집기 확장 지점](../extensibility/language-service-and-editor-extension-points.md)