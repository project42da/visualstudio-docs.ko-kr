---
title: "배송 Visual Studio 확장 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "VSIX 배포"
  - "VSIX 배포"
  - "VSIX 패키지에서 위성 Dll"
ms.assetid: 13cd263d-25f7-488e-9c1a-cff908caedb6
caps.latest.revision: 26
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 26
---
# 배송 Visual Studio 확장
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

확장 프로그램 개발을 완료 한 후 다른 컴퓨터에 설치할 친구 및 동료와 공유 하거나 Visual Studio 갤러리에 게시할 수 있습니다. 이 섹션에서는 게시 하 고 확장을 유지 하기 위해 수행 해야 하는 모든 항목 설명:.vsix 파일을 게시 하 고, 지역화, 업데이트를 사용 합니다.  
  
## VSIX 확장 사용  
 빈 VSIX 프로젝트를 만들고 다음을 다른 항목 템플릿을 추가 하 여 VSIX 확장을 만들 수 있습니다. 자세한 내용은 [VSIX 프로젝트 템플릿](../extensibility/vsix-project-template.md)을 참조하세요.  
  
 프로젝트 템플릿을 패키지, 말하면 VSPackages, 프레임 워크 MEF \(Managed Extensibility\) 구성 요소 항목을 VSIX 형식을 사용 하 여 **도구 상자** 컨트롤, 어셈블리 및 사용자 지정 형식 \(예: 사용자 지정 시작 페이지\). VSIX 형식 파일 기반 배포를 사용합니다. VSIX 패키지에 대 한 자세한 내용은 참조 [VSIX 패키지에 대 한 분석](../extensibility/anatomy-of-a-vsix-package.md)합니다.  
  
 VSIX 형식 코드 조각의 설치를 지원 하지 않습니다. 전역 어셈블리 캐시 \(GAC\)에 또는 시스템 레지스트리를 작성 하는 등 다른 시나리오도 지원 하지 않습니다. GAC 또는 설치에서 레지스트리를 작성 해야 할 경우에 Windows Installer를 사용 해야 합니다. 자세한 내용은 [Windows Installer 배포에 대 한 확장을 준비 하는 중](../extensibility/preparing-extensions-for-windows-installer-deployment.md)을 참조하세요.  
  
## Visual Studio 갤러리에 확장 게시  
 .Vsix 파일을 우편물 하거나 서버에 저장 하면 다른 사용자에 게 확장 프로그램을 배포할 수 있습니다. 많은 사람들이의 손에 코드 하는 가장 좋은 방법은에 넣을 이지만 [Visual Studio 갤러리](http://go.microsoft.com/fwlink/?LinkID=123847)합니다. Visual Studio 갤러리 확장을 통해 Visual Studio 사용자에 게 사용할 수 **확장 및 업데이트**합니다. 자세한 내용은 [Visual Studio 확장 찾기 및 사용](../ide/finding-and-using-visual-studio-extensions.md)을 참조하십시오.  
  
 Visual Studio 갤러리에 확장을 업로드 하는 방법을 보여 주는 전체 예제를 보려면 [연습: Visual Studio 확장 게시](../extensibility/walkthrough-publishing-a-visual-studio-extension.md)합니다.  
  
## 개인 갤러리  
 컨트롤, 템플릿 및 도구를 개발할 때 인트라넷에 개인 갤러리에 게시 하 여 조직의와 공유할 수 있습니다. 자세한 내용은 [개인 갤러리](../extensibility/private-galleries.md)을 참조하세요.  
  
## 확장 프로그램을 지역화  
 다른 로캘에서 확장을 해제 하려는 경우 그 지역화 하는 것이 좋습니다. 에 대 한 설명은 관련 작업을 참조 하십시오. [VSIX 패키지 지역화](../extensibility/localizing-vsix-packages.md)합니다.  
  
## 업데이트 및 버전 관리 확장 프로그램  
 확장 프로그램을 게시 한 후 한 번 업데이트 해야 할 때 제공 됩니다. Visual Studio 갤러리에 게시 된 확장을 업데이트 하는 방법을 알아보려면 참조 [방법: 확장 업데이트](../extensibility/how-to-update-a-visual-studio-extension.md)합니다.  
  
 Visual Studio의 여러 버전을 지원 하도록 확장 프로그램을 설정할 수 있습니다. 자세한 내용은 [여러 버전의 Visual Studio 지원](../extensibility/supporting-multiple-versions-of-visual-studio.md)을 참조하십시오.  
  
## 관련 항목  
  
|제목|설명|  
|--------|--------|  
|[VSIX 프로젝트 템플릿을 사용 하 여 시작 하기](../extensibility/getting-started-with-the-vsix-project-template.md)|사용자 지정 프로젝트 템플릿을 설치 하려면 VSIX 프로젝트 템플릿을 사용 하는 방법에 설명 합니다.|  
|[VSIX 패키지에 대 한 분석](../extensibility/anatomy-of-a-vsix-package.md)|VSIX 패키지의 구성 요소에 설명 합니다.|  
|[VSIX 프로젝트 템플릿](../extensibility/vsix-project-template.md)|패키지 및 게시를 확장 하는 방법에 대 한 단계별 지침을 제공 합니다.|  
|[VSIX 패키지 지역화](../extensibility/localizing-vsix-packages.md)|Extension.vsixlangpack 파일을 사용 하 여 설치 프로세스에 대 한 지역화 된 텍스트를 제공 하는 방법에 설명 합니다.|  
|[방법: 확장 업데이트](../extensibility/how-to-update-a-visual-studio-extension.md)|시스템에서 확장을 업데이트 하는 방법 및 기존 Visual Studio 확장에 대 한 업데이트를 배포 하는 방법을 설명 합니다.|  
|[방법: VSIX 패키지에 대 한 종속성 추가](../extensibility/how-to-add-a-dependency-to-a-vsix-package.md)|VSIX 배포 패키지에 대 한 참조를 추가 하는 방법에 설명 합니다.|  
|[Windows Installer 배포에 대 한 확장을 준비 하는 중](../extensibility/preparing-extensions-for-windows-installer-deployment.md)|Windows Installer와 함께 확장 프로그램을 배포 하는 방법에 설명 합니다.|  
|[VSIX 패키지 서명](../extensibility/signing-vsix-packages.md)|VSIX 패키지를 서명 하는 방법에 설명 합니다.|  
|[개인 갤러리](../extensibility/private-galleries.md)|확장에 대 한 개인 갤러리를 만드는 방법에 설명 합니다.|  
|[여러 버전의 Visual Studio 지원](../extensibility/supporting-multiple-versions-of-visual-studio.md)|여러 버전의 Visual Studio 확장 지원 하도록 하는 방법을 보여 줍니다.|