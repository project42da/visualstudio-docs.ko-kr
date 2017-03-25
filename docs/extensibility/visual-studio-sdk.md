---
title: "Visual Studio SDK | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VSSDK.v90.StartPage
helpviewer_keywords:
- Visual Studio SDK
- VS SDK (see Visual Studio SDK)
- Visual Studio, SDK
ms.assetid: 1f7c348a-114c-4243-b392-3531e9c9c6fd
caps.latest.revision: 56
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
ms.sourcegitcommit: 8163a0e1230712734936b7548bef1753ee0c1d2a
ms.openlocfilehash: b3cd444e48893057a057c39c515e51ff8b509b34
ms.lasthandoff: 03/07/2017

---
# <a name="visual-studio-sdk"></a>Visual Studio SDK
Visual Studio SDK를 사용 하면 Visual Studio 기능을 확장 하거나 Visual Studio에 새 기능을 통합할 수 있습니다. 다른 사용자에 게 및 Visual Studio 갤러리에 확장 프로그램을 배포할 수 있습니다. 다음은 Visual Studio를 확장할 수 있는 몇 가지 방법입니다.  
  
-   IDE에 명령, 단추, 메뉴 및 기타 UI 요소를 추가 합니다.  
  
-   새로운 기능에 대 한 도구 창 추가  
  
-   지정된 된 언어에 대 한 IntelliSense를 확장 하거나 새 프로그래밍 언어에 대 한 IntelliSense를 제공 합니다.  
  
-   전구를 사용 하 여 힌트 및 개발자는 데 도움이 되는 제안 사항 보다 효율적인 코드를 작성할 수 있도록  
  
-   새 언어에 대 한 지원을 사용 하도록 설정  
  
-   사용자 지정 프로젝트 형식 추가  
  
-   수백만 명의 개발자가 Visual Studio 갤러리를 통해 도달  
  
 이러한 기능에 대 한 자세한 정보를 찾아야 하기 전에 Visual Studio 확장을 작성해 본 경험이 있는 경우 [Visual Studio 확장을 개발 하기 시작](../extensibility/starting-to-develop-visual-studio-extensions.md)합니다.  
  
## <a name="installing-the-visual-studio-sdk"></a>Visual Studio SDK 설치  
 Visual Studio SDK는 Visual Studio 설치 프로그램의 선택적 기능입니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 참조 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)합니다.  
  
## <a name="whats-new-in-the-visual-studio-2017-sdk"></a>Visual Studio 2017 SDK의 새로운 기능  
 Visual Studio SDK에 주요 변경 내용 확장을 업데이트 해야 할 수도 있습니다 뿐만 아니라 간단한 솔루션 로드 및 VSIX v3 형식에 대 한 지원과 같은 몇 가지 새로운 기능이 있습니다. 자세한 내용은 참조 [Visual Studio 2017 SDK의 새로운](../extensibility/what-s-new-in-the-visual-studio-2017-sdk.md)합니다.  
  
## <a name="visual-studio-user-experience-guidelines"></a>Visual Studio 사용자 환경 지침  
 확장에 대 한 UI를 디자인 하기 위한 유용한 팁을 확인 [Visual Studio 사용자 환경 지침](../extensibility/ux-guidelines/visual-studio-user-experience-guidelines.md)합니다.  
  
 높은 DPI 장치에서 보기 좋게 하 여 확장 하는 방법을 알아볼 수 있습니다 우리의 [DPI 문제 해결](../extensibility/addressing-dpi-issues2.md) 항목입니다.  
  
 활용 하기 위해는 [이미지 서비스 및 카탈로그](../extensibility/image-service-and-catalog.md) 훌륭한 이미지 관리 및 높은 DPI 및 테마에 대 한 지원.  
  
## <a name="finding-and-installing-existing-visual-studio-extensions"></a>기존 Visual Studio 확장 찾기 및 설치  
 Visual Studio 확장을 찾을 수는 **확장 및 업데이트** 에서 대화 상자는 **도구** 메뉴. 자세한 내용은 참조 [찾기 및 Visual Studio Extensions를 사용 하 여](../ide/finding-and-using-visual-studio-extensions.md)합니다. 확장을 찾을 수 있습니다는 [Visual Studio 갤러리](https://visualstudiogallery.msdn.microsoft.com/)  
  
## <a name="visual-studio-sdk-reference"></a>Visual Studio SDK 참조  
 에 있는 Visual Studio SDK API 참조를 찾을 수 있습니다 [Visual Studio SDK 참조](../extensibility/visual-studio-sdk-reference.md)합니다.  
  
## <a name="visual-studio-sdk-samples"></a>Visual Studio SDK 샘플  
 GitHub에서 VS SDK 확장의 오픈 소스 예제를 확인할 수 [Visual Studio 샘플](https://aka.ms/vs2015sdksamples)합니다. 이 GitHub 리포지토리는 Visual Studio에서 다양 한 확장 가능한 기능을 보여 주는 샘플이 포함 되어 있습니다.  
  
## <a name="other-visual-studio-sdk-resources"></a>다른 Visual Studio SDK 리소스  
 사용할 수는 VSSDK에 대 한 질문이 확장 개발 경험을 공유 하려는 경우는 [Visual Studio 확장성 포럼](https://social.msdn.microsoft.com/Forums/vstudio/home?forum=vsx) 또는 [ExtendVS 그룹 채팅](https://gitter.im/Microsoft/extendvs)합니다.  
  
 자세한 정보를 찾을 수는 [VSX 실수가 블로그](http://blogs.msdn.com/b/vsx/) 수의 Microsoft Mvp가 작성 하는 블로그:  
  
-   [즐겨 찾는 Visual Studio 확장](http://geekswithblogs.net/sdorman/archive/2014/10/05/favorite-visual-studio-extensions.aspx)  
  
-   [Visual Studio 확장성](http://www.visualstudioextensibility.com/overview/vs/)  
  
-   [Visual Studio 확장](http://blog.slaks.net/2013-10-18/extending-visual-studio-part-1-getting-started/)  
  
## <a name="see-also"></a>참고 항목  
 [메뉴 명령을 사용 하 여 확장 만들기](../extensibility/creating-an-extension-with-a-menu-command.md)   
 [방법: Visual Studio 2017 확장성 프로젝트 마이그레이션](../extensibility/how-to-migrate-extensibility-projects-to-visual-studio-2017.md)   
 [FAQ: VSPackage 확장으로 추가 기능 변환](../extensibility/faq-converting-add-ins-to-vspackage-extensions.md)   
 [관리 코드에서 여러 스레드를 관리합니다.](../extensibility/managing-multiple-threads-in-managed-code.md)   
 [확장 메뉴 및 명령](../extensibility/extending-menus-and-commands.md)   
 [도구 모음에 명령 추가](../extensibility/adding-commands-to-toolbars.md)   
 [확장 및 도구 창을 사용자 지정](../extensibility/extending-and-customizing-tool-windows.md)   
 [편집기와 언어 서비스 확장](../extensibility/editor-and-language-service-extensions.md)   
 [프로젝트 확장](../extensibility/extending-projects.md)   
 [확장 사용자 설정 및 옵션](../extensibility/extending-user-settings-and-options.md)   
 [사용자 지정 프로젝트 및 항목 템플릿 만들기](../extensibility/creating-custom-project-and-item-templates.md)   
 [속성 및 속성 창 확장](../extensibility/extending-properties-and-the-property-window.md)   
 [Visual Studio의 다른 부분을 확장합니다.](../extensibility/extending-other-parts-of-visual-studio.md)   
 [사용 하 고 서비스를 제공 합니다.](../extensibility/using-and-providing-services.md)   
 [Vspackage를 관리합니다.](../extensibility/managing-vspackages.md)   
 [Visual Studio Shell 격리](../extensibility/visual-studio-isolated-shell.md)   
 [배송 Visual Studio 확장](../extensibility/shipping-visual-studio-extensions.md)   
 [Visual studio SDK](../extensibility/internals/inside-the-visual-studio-sdk.md)   
 [Visual Studio SDK에 대 한 지원](../extensibility/support-for-the-visual-studio-sdk.md)   
 [보관 파일](../extensibility/archive.md)   
 [Visual Studio SDK 참조](../extensibility/visual-studio-sdk-reference.md)
