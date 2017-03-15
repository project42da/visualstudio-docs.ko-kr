---
title: "언어 서비스 및 편집기 확장 시작 | Microsoft 문서"
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
caps.latest.revision: 21
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
ms.sourcegitcommit: 5658ecf52637a38bc3c2a5ad9e85b2edebf7d445
ms.openlocfilehash: 3cc009e23d123f50b108533e135bd51e123b3809
ms.lasthandoff: 02/22/2017

---
# <a name="getting-started-with-language-service-and-editor-extensions"></a>언어 서비스 및 편집기 확장 시작
사용자 프로그래밍 언어 또는 모든 콘텐츠 형식은 개요, 중괄호 일치, IntelliSense 및 전구 같은 언어 서비스 기능을 추가 하려면 편집기 확장을 사용할 수 있습니다. 모양 및 동작의 예를 들어 텍스트 색 지정, 여백, 장식, 및 기타 시각적 요소 Visual Studio 편집기를 사용자 지정할 수도 있습니다. 고유한 유형의 콘텐츠를 정의 하 고 모양 및 동작의 콘텐츠 표시 되는 텍스트 뷰를 지정할 수도 있습니다.  
  
 편집기 확장을 쓸 시작 하려면 Visual Studio SDK의 일부로 설치 된 편집기 프로젝트 템플릿을 사용 합니다. Visual Studio SDK는 다운로드 가능한 도구 집합을 쉽게 Vspackage를 사용 하 여 또는 관리 되는 확장성 프레임 워크 (MEF)를 사용 하 여 Visual Studio 확장 프로그램을 개발 하는 경우  
  
> [!NOTE]
>  Visual Studio SDK에 대 한 자세한 내용은 참조 [Visual Studio SDK](../extensibility/visual-studio-sdk.md)합니다.  
  
 사용자 고유의 편집기 확장을 작성 하기 전에 다음과 같은 개념 및 기술에 대해서는 것이 좋습니다.  
  
## <a name="the-windows-presentation-foundation-wpf-and-editor-extensions"></a>Windows Presentation Foundation (WPF) 및 편집기 확장  
 Visual Studio 편집기 사용자 인터페이스 (UI)는 Windows Presentation Foundation (WPF)를 사용 하 여 구현 됩니다. WPF는 풍부한 시각적 환경 및 비즈니스 논리에서 코드의 시각적 측면을 구분 하는 일관성 있는 프로그래밍 모델을 제공 합니다. 편집기 확장을 만들 때 여러 가지 WPF 요소와 기능을 사용할 수 있습니다. 자세한 내용은 참조 [Windows Presentation Foundation](http://msdn.microsoft.com/Library/f667bd15-2134-41e9-b4af-5ced6fafab5d)합니다.  
  
## <a name="the-managed-extensibility-framework-mef-and-editor-extensions"></a>관리 되는 확장성 프레임 워크 (MEF) 및 편집기 확장  
 Visual Studio 편집기는 프레임 워크 MEF (Managed Extensibility)를 사용 하 여 구성 요소와 확장을 관리 합니다. 또한는 MEF에는 개발자가 더 쉽게 Visual Studio와 같은 호스트 응용 프로그램에 대 한 확장을 만들 수 있습니다. 이 프레임 워크에서는 MEF 계약에 따라 확장을 정의 하 고 MEF 구성 요소 부분으로 내보내기. 호스트 응용 프로그램을 찾아서, 등록, 올바른 컨텍스트에 적용 되는 선택 되어 있는지 확인 하 구성 요소 부분을 관리 합니다.  
  
> [!NOTE]
>  편집기에서 MEF에 대 한 자세한 내용은 참조 [편집기에서 Managed Extensibility Framework](../extensibility/managed-extensibility-framework-in-the-editor.md)합니다.  
  
## <a name="visual-studio-editor-extension-points-and-extensions"></a>Visual Studio 편집기 확장 점 및 확장  
 편집기 확장 요소가 있는 MEF 구성 요소 파트를 사용자 지정 및 확장할 수 있습니다. 일부 경우에 인터페이스를 구현 하 고 올바른 메타 데이터와 함께 내보내기 확장 지점을 확장 합니다. 다른 경우에만 선언 하 확장 고 특정 형식으로 내보냅니다.  
  
 다음은 몇 가지 기본 종류의 편집기 확장입니다.  
  
-   여백 및 스크롤 막대  
  
-   Tags  
  
-   도구 영역  
  
-   옵션  
  
-   IntelliSense  
  
 편집기 확장 지점에 대 한 자세한 내용은 참조 [언어 서비스 및 편집기 확장 지점이](../extensibility/language-service-and-editor-extension-points.md)합니다.  
  
## <a name="deploying-editor-extensions"></a>편집기 확장 배포  
 Visual Studio에서 솔루션을 빌드할 솔루션에 source.extension.vsixmanifest 라는 메타 데이터 파일을 추가 하 고 다음 Visual Studio로 알려져 있는 폴더에 이진 파일 및 매니페스트의 복사본을 추가 하 여 편집기 확장을 배포 합니다. 매니페스트 파일 (예를 들어, 이름, 저자, 버전 및 콘텐츠 유형에) 확장에 대 한 기본적인 사항을 정의합니다. VSIX 매니페스트 파일 및 확장을 배포 하는 방법에 대 한 자세한 내용은 참조 [Visual Studio 확장 배송](../extensibility/shipping-visual-studio-extensions.md)합니다.  
  
 컴퓨터에 확장을 설치할 때 Visual Studio로 알려져 있는 폴더의 하위 폴더에 이진 파일 및 매니페스트가 포함 됩니다.  
  
> [!WARNING]
>  Visual Studio에 포함 된 편집기 확장성 템플릿 중 하나를 사용 하는 경우에 매니페스트 및 배포 위치에 대 한 세부 정보를 걱정할 필요가 없습니다. 템플릿을 등록 하 고 확장을 배포 하는 데 필요한 모든 내용을 포함 합니다.  
  
## <a name="running-extensions-in-the-experimental-instance"></a>실험적 인스턴스에서 확장을 실행합니다.  
 (Windows Vista 및 Windows 7)에서 다음 실험 폴더에 배포 하 여 확장을 개발 하는 동안 Visual Studio의 작업 버전을 느끼지 수 있습니다.:  
  
 *% LOCALAPPDATA %*\VisualStudio\10.0Exp\Extensions\\*회사*\\*확장 Id*  
  
 여기서 *% LOCALAPPDATA %* 로그온 한 사용자의 이름인 *회사* 확장명을 소유 하는 회사의 이름 및 *확장 Id* 확장의 ID입니다.  
  
 실험적 위치에 확장을 배포할 때 디버그 모드에서 실행 됩니다. Visual Studio의 두 번째 인스턴스를 시작 하 고 라는 **Microsoft Visual Studio 실험적 인스턴스**합니다.  
  
## <a name="managing-extensions"></a>확장 관리  
 Visual Studio에 대 한 확장에 나열 된 **확장 및 업데이트** (에 **도구** 메뉴). 실험적 인스턴스에서 확장을 테스트 하는 경우에 표시 됩니다 **확장 및 업데이트** 실험적 인스턴스에서 하지만 개발 인스턴스에 나타나지 않습니다.  
  
 자세한 내용은 참조 [찾기 및 Visual Studio Extensions를 사용 하 여](../ide/finding-and-using-visual-studio-extensions.md)합니다.  
  
## <a name="using-templates-to-create-editor-extensions"></a>편집기 확장을 만드는 템플릿을 사용 하 여  
 분류자, 장식, 및 여백 사용자 지정 하는 MEF 확장을 만드는 편집기 템플릿을 사용할 수 있습니다. C# 및 Visual Basic 프로젝트에 대 한 템플릿이 있습니다. 자세한 내용은 참조 [편집기 항목 템플릿을 사용 하 여 확장을 만드는](../extensibility/creating-an-extension-with-an-editor-item-template.md)합니다.  
  
 또한 확장을 만드는 VSIX 프로젝트 템플릿을 사용할 수 있습니다. 이 서식 파일에는 모든 종류의 확장 프로그램을 배포 하 고 source.extension.vsixmanifest 파일, 필요한 어셈블리 참조 및 확장을 배포할 수 있도록 하는 빌드 작업을 포함 하는 프로젝트 파일을 포함 하는 데 필요한 요소에만 제공 합니다. 자세한 내용은 참조 [VSIX 프로젝트 템플릿은](../extensibility/vsix-project-template.md)합니다.  
  
 작업을 Visual Studio 패키지 확장 프로그램에서 MEF 구성 요소 편집기도 만들 수도 있습니다. 자세한 내용은 다음 연습을 참조 합니다.  
  
-   [연습: 편집기 확장 셸 명령 사용](../extensibility/walkthrough-using-a-shell-command-with-an-editor-extension.md)  
  
-   [연습: 편집기 확장에 바로 가기 키 사용](../extensibility/walkthrough-using-a-shortcut-key-with-an-editor-extension.md)  
  
## <a name="see-also"></a>참고 항목  
 [언어 서비스 및 편집기 확장 지점](../extensibility/language-service-and-editor-extension-points.md)
