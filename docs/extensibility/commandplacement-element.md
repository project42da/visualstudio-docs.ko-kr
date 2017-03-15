---
title: "CommandPlacement 요소 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "CommandPlacements 요소 (VSCT XML 스키마)"
  - "VSCT XML 스키마 요소, CommandPlacements"
ms.assetid: 2cbd7ac8-c55a-43d8-a26d-713b3d790016
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# CommandPlacement 요소
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

CommandPlacement 요소 단추, 그룹 및 메뉴 둘 이상의 그룹 또는 메뉴에 포함 될 수 있습니다. CommandPlacement 요소를 사용 하 여 사용자 인터페이스의 모양을 수정 하려면 이러한 항목을 완전히 다시 정의할 필요가 없습니다.  
  
 자세한 내용은 [단추의 다시 사용할 수 있는 그룹 만들기](../extensibility/creating-reusable-groups-of-buttons.md)을 참조하십시오.  
  
## 구문  
  
```  
<CommandPlacement guid=guidMyCommandSet" id="MyCommand" priority="0x001" >  
  <Parent>... </Parent>  
</CommandPlacement>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|guid|필수 요소. 에 정의 된 명령 집합의 guid는 [기호 요소](../extensibility/symbols-element.md)합니다.|  
|ID|필수 요소. 메뉴, 그룹 또는 명령에 정의 된 대로 배치할의 id는 `Symbols Element`합니다.|  
|priority|필수 요소. 부모 요소에는 항목의 표시 위치를 결정합니다.|  
|조건|선택적 요소.[조건부 특성](../extensibility/vsct-xml-schema-conditional-attributes.md)을 참조하세요.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|부모|필수 요소. 메뉴 또는 그룹을 호스팅하는 항목을 배치할 수 있습니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[CommandPlacements 요소](../extensibility/commandplacements-element.md)|CommandPlacements 및 CommandPlacement 요소 그룹을 지정합니다.|  
  
## 예제  
  
```  
<CommandPlacements> <CommandPlacement guid="guidWidgetPackage" id="cmdidInsertOptions" priority="0x0300"> <Parent guid="cmdGuidWidgetCommands" id="menuIDEditWidget"/> </CommandPlacement> </CommandPlacements>  
```  
  
## 참고 항목  
 [CommandPlacements 요소](../extensibility/commandplacements-element.md)   
 [Visual Studio 명령 테이블 \(. Vsct\) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)