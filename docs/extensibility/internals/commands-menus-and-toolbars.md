---
title: "명령, 메뉴 및 도구 모음 | Microsoft Docs"
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
  - "메뉴 [Visual Studio SDK] 명령"
  - "명령[Visual Studio]"
  - "도구 모음 [Visual Studio] 명령"
ms.assetid: 07b4ed90-dbbd-40df-b6c9-8395fd6f2ab6
caps.latest.revision: 60
caps.handback.revision: 60
ms.author: "gregvanl"
manager: "ghogen"
---
# 명령, 메뉴 및 도구 모음
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

메뉴 및 도구 모음 방식으로 사용자 명령 VSPackage에 액세스 됩니다. 명령에는 문서를 인쇄, 보기, 새로 고침 또는 새 파일을 만드는 등의 작업을 수행 하는 함수입니다. 메뉴 및 도구 모음 가지 편리한 그래픽 명령을 사용자에 게 제공할 수 있습니다. 일반적으로 같은 메뉴 또는 도구 모음에서 관련된 명령은 함께 클러스터 됩니다.  
  
-   메뉴는 일반적으로 통합된 개발 환경 \(IDE\) 또는 도구 창 맨 아래에 있는 행에 클러스터 된 한 단어 문자열로 표시 됩니다. 또한 메뉴를 마우스 오른쪽 단추 클릭 이벤트의 결과로 표시 하 고 해당 컨텍스트 내에서 바로 가기 메뉴는 라고 합니다. 화살표를 클릭 하면 메뉴 명령을 하나 이상 표시 하려면 확장 합니다. 명령에 화살표를 클릭 하면 작업을 수행 하거나 추가 명령을 포함 하는 하위 메뉴를 시작할 수 있습니다. 잘 알려진 메뉴 이름 중 일부 파일, 편집, 보기 및 창 됩니다. 자세한 내용은 [확장 메뉴 및 명령](../../extensibility/extending-menus-and-commands.md)을 참조하세요.  
  
-   일반적으로 도구 모음 단추 및 콤보 상자, 목록 상자, 텍스트 상자 및 메뉴 컨트롤러와 같은 다른 컨트롤의 행을 됩니다. 모든 도구 모음 컨트롤이 명령에 연결 됩니다. 도구 모음 단추를 클릭 하면 해당 관련 된 명령이 활성화 됩니다. 일반적으로 도구 모음 단추에는 인쇄 명령에 대 한 프린터와 같은 기본 명령을 제안 하는 아이콘이 있습니다. 드롭다운 목록 컨트롤에는 목록의 각 항목에에서는 다른 명령 연관 됩니다. 메뉴 컨트롤러는 컨트롤의 한 쪽은 도구 모음 단추 및 다른 측면은 아래쪽 화살표를 클릭 하면 추가 명령을 표시 하는 하이브리드입니다. 자세한 내용은 [도구 모음에 메뉴 컨트롤러 추가](../../extensibility/adding-a-menu-controller-to-a-toolbar.md)을 참조하십시오.  
  
-   명령을 만들면 사용자도 만들어야 이벤트 처리기에 대 한 합니다. 해당 텍스트를 수정할 수 있습니다 명령을 표시 되거나, 설정 된 경우 이벤트 처리기를 결정 하 고 명령 적절히 응답 하는지 확인 \("경로"\) 활성화 합니다. 대부분의 경우에서 IDE를 사용 하 여 명령을 처리는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 인터페이스입니다. 에 명령 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 로컬 선택을 기반으로 하 고 전역 선택을 기반으로 하는 가장 바깥쪽 컨텍스트를 진행 하는 가장 안쪽의 명령 컨텍스트를부터 계층 방식으로 경로입니다. 주 메뉴에 추가 된 주석은 스크립팅을 위해 바로 사용할 수 있습니다. 자세한 내용은 [MenuCommand 및 OleMenuCommand](../../misc/menucommands-vs-olemenucommands.md) 및 [컨텍스트 개체 선택](../../extensibility/internals/selection-context-objects.md)를 참조하세요.  
  
 새 메뉴 및 도구 모음을 정의 하려면 Visual Studio 명령 테이블 \(.vsct\) 파일에 설명 해야 있습니다. Visual Studio 패키지 템플릿을 어떤 명령, 도구 모음 및 서식 파일에서 선택한 편집기를 지 원하는 데 필요한 요소와 함께 자동으로이 파일을 만듭니다. 또는 작성할 수 있습니다 고유한.vsct 파일 여기 설명 하는 xml 스키마를 사용 하 여: [VSCT XML 스키마 참조](../../extensibility/vsct-xml-schema-reference.md)합니다.  
  
 .Vsct 파일을 사용 하는 방법에 대 한 자세한 내용은 참조 [Visual Studio 명령 테이블 \(. Vsct\) 파일](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)합니다.  
  
 이 섹션의 항목에서는 명령, 메뉴 및 도구 모음 Vspackage에서 작동 하는 방법을 설명 합니다.  
  
## 단원 내용  
 [Vspackage에서 사용자 인터페이스 요소를 추가 하는 방법](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)  
 자세한 설명은 명령 테이블 형식 지정 합니다.  
  
 [Visual Studio 명령 테이블 \(. Vsct\) 파일](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)  
 XML 기반 구문 및 컴파일러에 명령 테이블에 설명 합니다.  
  
 [기본 명령, 그룹 및 도구 모음 배치](../../extensibility/internals/default-command-group-and-toolbar-placement.md)  
 미리 정의 된 명령, 그룹, 메뉴 및 도구 모음에 설명 합니다.  
  
 [IDE 정의 명령, 메뉴 및 그룹](../../extensibility/internals/ide-defined-commands-menus-and-groups.md)  
 미리 정의 된 메뉴, 명령 및 명령 그룹에서 사용할 수 있는 지정 된 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE입니다.  
  
 [명령 디자인](../../extensibility/internals/command-design.md)  
 명령을 디자인 하는 방법에 설명 합니다.  
  
 [메뉴 및 도구 모음 명령 최적화](../../extensibility/internals/optimizing-menu-and-toolbar-commands.md)  
 명령에 대 한 지침을 제공합니다.  
  
 [명령을 사용 가능](../../extensibility/internals/making-commands-available.md)  
 Visual Studio로 명령을 사용할 수 있도록 하는 방법에 설명 합니다.  
  
 [명령 및 Interop 어셈블리를 사용 하는 메뉴](../../extensibility/internals/commands-and-menus-that-use-interop-assemblies.md)  
 Interop 어셈블리를 사용 하는 명령을 구현 하는 방법에 설명 합니다.  
  
## 관련 단원  
 [Vspackage의 명령 라우팅](../../extensibility/internals/command-routing-in-vspackages.md)  
 명령 라우팅 Vspackage에 설명 합니다.