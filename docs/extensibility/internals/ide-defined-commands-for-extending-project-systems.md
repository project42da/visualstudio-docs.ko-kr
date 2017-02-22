---
title: "프로젝트 시스템 확장을 위한 IDE 정의 명령 | Microsoft Docs"
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
  - "명령, 프로젝트 시스템"
  - "프로젝트 시스템, 명령 환경 정의"
ms.assetid: 0e33b8e9-16fa-4400-a941-e92d56120e7e
caps.latest.revision: 19
caps.handback.revision: 19
ms.author: "gregvanl"
manager: "ghogen"
---
# 프로젝트 시스템 확장을 위한 IDE 정의 명령
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

프로젝트 시스템을 확장할 때 명령을 사용 하 여 한 명령에서 제공 하는 그룹은 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE.  
  
 다음 섹션에서는 프로젝트 시스템 확장에 특히 유용한 명령 항목을 나열 합니다.  
  
## 명령 메뉴  
 다음 표에서 유용한 위치 프로젝트 extender를 호출 하는 상위 수준의 명령을 추가 하는 명령 메뉴를 표시 합니다.  
  
|명령 메뉴|설명|  
|-----------|--------|  
|IDM\_VS\_MENU\_PROJECT|해당  **프로젝트** 최상위 메뉴입니다.|  
|IDM\_VS\_TOOL\_PROJWIN|해당  **솔루션 탐색기** 도구 모음입니다.|  
  
## 바로 가기 메뉴  
 단일 노드를 선택 하면 해당 바로 가기 메뉴는 다음과 같습니다의  **솔루션 탐색기**, 또는에 형식이 같은 여러 선택 영역이 있는 경우는  **솔루션 탐색기**, 같은 종류의 모든 선택한 노드가 될 때입니다.  
  
|바로 가기 메뉴|설명|  
|--------------|--------|  
|<xref:Microsoft.VisualStudio.Shell.VsMenus.IDM_VS_CTXT_PROJNODE>|프로젝트 노드를 선택한 경우에 적용 됩니다.|  
|<xref:Microsoft.VisualStudio.Shell.VsMenus.IDM_VS_CTXT_ITEMNODE>|파일이 선택 된 경우에 적용 됩니다.|  
|<xref:Microsoft.VisualStudio.Shell.VsMenus.IDM_VS_CTXT_FOLDERNODE>|폴더를 선택 하는 경우에 적용 됩니다.|  
|IDM\_VS\_CTXT\_WEBREFFOLDER|웹 참조 폴더를 선택한 경우에 적용 됩니다.|  
|<xref:Microsoft.VisualStudio.Shell.VsMenus.IDM_VS_CTXT_REFERENCEROOT>|"참조" 이라는 참조가 루트 노드를 선택한 경우에 적용 됩니다.|  
|<xref:Microsoft.VisualStudio.Shell.VsMenus.IDM_VS_CTXT_REFERENCE>|참조 노드를 선택한 경우에 적용 됩니다. 여기에 어셈블리, COM 및 프로젝트 참조만 포함 됩니다.  웹 참조를 포함 하지 않습니다.|  
  
 다음 표에서 적용할 때 바로 가기 메뉴 선택 영역에는  **솔루션 탐색기** 여러 계층에 걸친  
  
|바로 가기 메뉴|설명|  
|--------------|--------|  
|IDM\_VS\_CTXT\_XPROJ\_SLNPROJ|현재 선택 영역의 솔루션 노드 및 루트 프로젝트 노드 포함 되어 있을 때 적용 됩니다.|  
|IDM\_VS\_CTXT\_XPROJ\_SLNITEM|솔루션 노드 및 프로젝트 항목은 현재 선택 영역을 포함 하는 경우에 적용 됩니다.|  
|IDM\_VS\_CTXT\_XPROJ\_MULTIPROJ|여러 프로젝트의 루트 노드는 현재 선택 영역의 구성 되어 있을 때만 적용 됩니다.|  
|IDM\_VS\_CTXT\_XPROJ\_PROJITEM|루트 프로젝트 노드 및 프로젝트 항목의 현재 선택 영역을 포함 하는 경우에 적용 됩니다.  또한 선택 영역이 솔루션 노드를 포함할 수 있습니다.|  
|IDM\_VS\_CTXT\_XPROJ\_MULTIITEM|솔루션에 여러 프로젝트에서 프로젝트 항목을 현재 선택 영역을 포함 하거나 같은 프로젝트에서 다른 형식의 항목을 선택한 경우에 적용 됩니다.|  
  
## 그룹 명령  
 다음 표에서 프로젝트를 확장 하 고를 통해 액세스할 수 있는 경우 사용할 수 있는 명령 그룹의 <xref:Microsoft.VisualStudio.Shell.VsMenus.IDM_VS_CTXT_PROJNODE> 바로 가기 메뉴입니다.  
  
|명령 그룹|설명|  
|-----------|--------|  
|IDG\_VS\_CTXT\_PROJECT\_BUILD|프로젝트 구성, 다시 구축 하기 위한 명령입니다.|  
|IDG\_VS\_CTXT\_COMPILELINK|컴파일 및 프로젝트를 연결 하는 방법에 대 한 명령입니다.|  
|IDG\_VS\_CTXT\_PROJECT\_CONFIG|프로젝트 구성을 설정 하 고 빌드 순서는 명령입니다.|  
|IDG\_VS\_CTXT\_PROJECT\_ADD|프로젝트에 항목을 추가 하는 명령입니다.|  
|IDG\_VS\_CTXT\_PROJECT\_START|F5 키와 연관 된 시작 프로젝트를 설정 하는 명령입니다.|  
|IDG\_VS\_CTXT\_PROJECT\_SAVE|프로젝트 항목을 저장 하는 명령입니다.|  
|IDG\_VS\_CTXT\_PROJECT\_DEBUG|디버깅에 대 한 명령입니다.|  
|IDG\_VS\_CTXT\_PROJECT\_SCC|소스 제어에 대 한 명령입니다.|  
|IDG\_VS\_CTXT\_PROJECT\_TRANSFER|잘라내기 명령을 복사 및 붙여넣기 작업.|  
|IDG\_VS\_CTXT\_PROJECT\_PROPERTIES|명령에 액세스할 수 있는  **프로젝트 속성**  대화 상자.|  
  
## 참고 항목  
 [Vspackage에서 사용자 인터페이스 요소를 추가 하는 방법](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [MenuCommand 및 OleMenuCommand](../../misc/menucommands-vs-olemenucommands.md)   
 [단추의 다시 사용할 수 있는 그룹 만들기](../../extensibility/creating-reusable-groups-of-buttons.md)