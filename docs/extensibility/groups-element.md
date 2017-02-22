---
title: "Groups 요소 | Microsoft Docs"
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
  - "VSCT XML 스키마 요소, 그룹"
  - "그룹 요소 (VSCT XML 스키마)"
ms.assetid: 740ca4ec-79fa-4b98-8f9a-2a137f9f7f98
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# Groups 요소
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Vspackage 명령 그룹을 정의 하는 항목을 포함 합니다.  
  
## 구문  
  
```  
<Groups>  
  <Group>... </Group>  
  <Group>... </Group>  
</Groups>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|조건|선택적 요소.[조건부 특성](../extensibility/vsct-xml-schema-conditional-attributes.md)을 참조하세요.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[그룹 요소](../extensibility/group-element.md)|단일 명령 그룹을 나타냅니다.|  
|[Groups Element](../extensibility/groups-element.md)|Vspackage 명령 그룹을 정의 하는 항목을 포함 합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[Commands 요소](../extensibility/commands-element.md)|VSPackage 도구 모음에 있는 명령의 컬렉션을 나타냅니다.|  
  
## 예제  
  
```  
<Groups> <Group guid="cmdSetGuidWidgetCommands" id="groupIDFileEdit"> <Parent guid="guidSHLMainMenu" id="IDM_VS_TOOL_MAINMENU"/> </Group> </Groups>  
```  
  
## 참고 항목  
 [Vspackage에서 사용자 인터페이스 요소를 추가 하는 방법](../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [명령, 메뉴 및 도구 모음](../extensibility/internals/commands-menus-and-toolbars.md)