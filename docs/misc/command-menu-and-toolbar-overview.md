---
title: "명령, 메뉴 및 도구 모음 개요 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "메뉴 기능[Visual Studio SDK]"
  - "도구 모음 기능[Visual Studio SDK]"
ms.assetid: cbdaceaa-7dd3-4a56-aea6-b759e48d83d6
caps.latest.revision: 19
caps.handback.revision: 19
manager: "douge"
---
# 명령, 메뉴 및 도구 모음 개요
메뉴 및 도구 모음은 사용자가 VSPackage의 명령에 액세스할 수 있는 편리한 그래픽 방법을 제공합니다. 명령은 문서 인쇄, 보기 새로 고침 또는 새 파일 만들기 등의 작업을 수행하는 함수입니다. 메뉴 및 도구 모음은 사용자에게 명령을 제공하는 편리한 그래픽 방법입니다. 일반적으로 관련 명령은 동일한 메뉴 또는 도구 모음에 함께 클러스터됩니다.  
  
-   메뉴는 일반적으로 IDE\(통합 개발 환경\) 또는 도구 창의 맨 위에 한 단어 문자열이 연속으로 클러스터되어 표시됩니다. 메뉴를 마우스 오른쪽 단추 클릭 이벤트의 결과로 표시할 수도 있으며, 해당 컨텍스트에서는 바로 가기 메뉴라고 합니다. 클릭하면 메뉴가 확장되어 하나 이상의 명령을 표시합니다. 명령을 클릭하여 작업을 수행하거나 추가 명령이 포함된 하위 메뉴를 시작할 수 있습니다. 잘 알려진 메뉴 이름에는 파일, 편집, 보기, 창 등이 있습니다. 자세한 내용은 [확장 메뉴 및 명령](../extensibility/extending-menus-and-commands.md)을 참조하세요.  
  
-   일반적으로 도구 모음은 단추와 콤보 상자, 목록 상자, 텍스트 상자 및 메뉴 컨트롤러와 같은 다른 컨트롤의 행입니다. 모든 도구 모음 컨트롤은 명령과 연결됩니다. 도구 모음 단추를 클릭하면 연결된 명령이 활성화됩니다. 인쇄 명령의 프린터와 같이 일반적으로 도구 모음 단추에는 기본 명령을 나타내는 아이콘이 있습니다. 드롭다운 목록 컨트롤에서 목록의 각 항목은 다른 명령과 연결됩니다. 메뉴 컨트롤러는 컨트롤의 한 쪽은 도구 모음 단추이고 다른 쪽은 클릭할 경우 추가 명령을 표시하는 아래쪽 화살표인 하이브리드입니다. 자세한 내용은 [방법: 도구 창을 위한 도구 모음 만들기](../misc/how-to-create-toolbars-for-tool-windows.md) 및 [메뉴 명령에 아이콘 추가](../extensibility/adding-icons-to-menu-commands.md)를 참조하세요.  
  
-   명령을 만드는 경우 해당 이벤트 처리기도 만들어야 합니다. 이벤트 처리기는 명령이 표시되거나 사용할 수 있는 경우를 결정하며, 해당 텍스트를 수정할 수 있게 하고, 활성화된 경우 명령이 적절히 응답\("라우팅"\)하도록 합니다. 대부분의 경우 IDE는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 인터페이스를 사용하여 명령을 처리합니다.[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]의 명령은 로컬 선택 기반의 가장 안쪽의 명령 컨텍스트부터 전역 선택 기반의 가장 바깥쪽 컨텍스트로 진행하는 계층적 방식으로 라우팅합니다. 주 메뉴에 추가된 명령은 즉시 스크립팅에 사용할 수 있습니다. 자세한 내용은 [MenuCommand 및 OleMenuCommand](../misc/menucommands-vs-olemenucommands.md) 및 [컨텍스트 개체 선택](../extensibility/internals/selection-context-objects.md)를 참조하세요.  
  
 새 메뉴 및 도구 모음을 정의하려면 Visual Studio 명령 테이블\(.vsct\) 파일에서 설명해야 합니다. Visual Studio 패키지 템플릿은 템플릿에서 선택한 명령, 도구 모음 및 편집기를 지원하는 데 필요한 요소와 함께 자동으로 이 파일을 만듭니다. 또는 [VSCT XML 스키마 참조](../extensibility/vsct-xml-schema-reference.md)에 설명된 xml 스키마를 사용하여 고유한 .vsct 파일을 작성할 수 있습니다.  
  
 .vsct 파일을 사용하는 방법에 대한 자세한 내용을 보려면 [Visual Studio 명령 테이블 \(. Vsct\) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)을 참조하거나 [사용자 인터페이스 요소에 대한 연습](../misc/walkthroughs-for-user-interface-elements.md) 중 하나를 시도하세요.  
  
 메뉴 및 도구 모음의 자세한 개요는 [명령 디자인](../extensibility/internals/command-design.md)를 참조하세요.  
  
## 참고 항목  
 [확장 메뉴 및 명령](../extensibility/extending-menus-and-commands.md)   
 [명령, 메뉴 및 도구 모음](../extensibility/internals/commands-menus-and-toolbars.md)   
 [Vspackage](../extensibility/internals/vspackages.md)