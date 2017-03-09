---
title: "확장명 분석기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "VSPackage, 로드 오류 분석기"
ms.assetid: 8d2bcc4e-9feb-45a5-8d8e-470346f0d39e
caps.latest.revision: 8
caps.handback.revision: 8
manager: "douge"
---
# 확장명 분석기
**확장 분석기**는 가장 일반적인 확장 로드 실패를 캡처 및 기록합니다.**확장 분석기**는 자체 도구 창에서 실행됩니다. 이 분석기는 실패의 이유 및 해결 방법에 대한 제안을 보고합니다.  
  
 [확장 분석기](http://go.microsoft.com/fwlink/?LinkId=205840)는 Visual Studio 갤러리에서 다운로드할 수 있습니다.**확장 분석기** 어셈블리는 \<*Visual Studio 설치 경로*\>\\Common7\\IDE\\PrivateAssemblies\\에 설치됩니다.  
  
## 브라우저  
 **확장 분석기**를 설치한 후 **도구** 메뉴에서 **확장 분석기**, **브라우저**를 차례로 클릭합니다. 컴퓨터에 등록된 모든 확장을 나열하는 창이 표시됩니다. VSIX 파일, VSPackages, PkgDef 파일, MEF 구성 요소에 대해 서로 다른 탭이 있습니다. 열 이름을 기준으로 목록을 정렬할 수 있습니다.  
  
1.  VSIX 탭에는 설치된 VSIX 확장에 대한 정보가 표시됩니다.**시스템 구성 요소 표시** 확인란을 선택하여 시스템 구성 요소를 포함할 수 있습니다. 이 탭에서는 VSIX에 대한 로그 항목으로 이동하고, Visual Studio XML 편집기에서 VSIX 매니페스트를 열고, VSIX 확장이 설치된 폴더를 열 수 있습니다.  
  
2.  VSPackages 탭은 로드 여부와 상관없이 현재 Visual Studio에 알려진 VSPackages에 대한 정보를 표시합니다. 이 정보는 VSIX 식별자, .pkgdef 파일, VSPackage의 GUID를 포함합니다.**시스템 패키지 표시** 확인란을 선택하여 시스템 VSPackages를 포함할 수 있습니다. 이 탭에서 로그 항목으로 이동하고, VSIX 탭에 나열된 VSIX를 보고, PkgDef 파일 탭의 .pkgdef 파일을 보고, VSPackage를 분석할 수 있습니다. 분석 결과는 **출력** 창에 표시됩니다.  
  
3.  PkgDef 파일 탭에는 Visual Studio에 알려진 확장의 .pkgdef 파일에 대한 정보가 표시됩니다. 이 정보는 VSIX 식별자 및 확장의 경로를 포함합니다. 로그 또는 VSIX 탭으로 이동할 수 있으며 편집기에서.pkgdef 파일을 볼 수 있습니다.  
  
4.  MEF 구성 요소 탭에는 Visual Studio에 알려진 MEF 구성 요소에 대한 정보가 표시됩니다. 이 정보는 VSIX 식별자 및 확장이 설치되어 있는 경로를 포함합니다.**시스템 구성 요소 표시** 확인란을 선택하여 시스템 구성 요소를 포함할 수 있습니다. 또한 해당 VSIX 항목, .pkgdef 파일 및 확장이 설치된 위치로 이동할 수 있습니다.  
  
> [!WARNING]
>  Fusion 로깅을 설정하라는 메시지가 나타날 수 있습니다. 이렇게 하려면 로그 파일의 위치를 선택합니다. 계속하기 전에 Visual Studio의 모든 인스턴스를 다시 시작하라는 메시지가 나타날 수 있습니다.  
  
## 로그 뷰어  
 프로젝트의 명령줄 인수에 \/log를 추가하여 로깅이 설정된 프로젝트를 실행 중인 경우 **확장 로그 뷰어**로 로깅 메시지를 볼 수 있습니다. 자세한 내용은 [\/Log](../ide/reference/log-devenv-exe.md)을 참조하세요.**확장 로그 뷰어** 창에는 날짜, 수신기, 항목 유형\(메시지 유형\), 오류 유형, 클래스\/인터페이스 정보 및 로그 메시지가 표시됩니다. 정보를 정렬 및 필터링할 수 있습니다.  
  
## 일반적인 확장 로드 문제  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 확장 로드 실패의 일반적인 몇 가지 이유는 다음과 같습니다.  
  
-   종속성 문제. 종속 어셈블리를 찾을 수 없는 방식으로 확장을 배포할 수도 있습니다.  
  
-   예외 VSPackage가 로드될 때 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A> 메서드를 호출합니다. 이 메서드가 예외를 throw하는 경우 VSPackage 로드가 실패합니다. 이 문제를 격리하는 가장 좋은 방법은 SetSite 코드를 단계별로 수행하는 것입니다.  
  
-   잘못된 등록. 확장이 적절하게 서명되었는지, VSPackage가 올바른 공개 키를 사용하여 등록되었는지 확인합니다.  
  
## 참고 항목  
 [Vspackage를 관리합니다.](../extensibility/managing-vspackages.md)