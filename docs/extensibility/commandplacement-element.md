---
title: CommandPlacement 요소 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- CommandPlacements element (VSCT XML schema)
- VSCT XML schema elements, CommandPlacements
ms.assetid: 2cbd7ac8-c55a-43d8-a26d-713b3d790016
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 49de1e1cb41c13ef9b587689f36e302bcadf890c
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2018
---
# <a name="commandplacement-element"></a>CommandPlacement 요소
CommandPlacement 요소에는 단추, 그룹 및 메뉴 둘 이상의 그룹이 나 메뉴에 포함 될 수 있습니다. CommandPlacement 요소를 사용 하 여 완전히 사용자 인터페이스의 모양을 수정 하기 위해 이러한 항목을 다시 정의할 필요가 없습니다.  
  
 자세한 내용은 참조 [단추의 다시 사용할 수 있는 그룹 만들기](../extensibility/creating-reusable-groups-of-buttons.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
<CommandPlacement guid="guidMyCommandSet" id="MyCommand" priority="0x001" >  
  <Parent>... </Parent>  
</CommandPlacement>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|guid|필수. 에 정의 된 명령 집합의 guid는 [기호 요소](../extensibility/symbols-element.md)합니다.|  
|ID|필수. 메뉴, 그룹 또는 명령에 정의 된 대로 배치할의 id는 `Symbols Element`합니다.|  
|priority|필수. 부모 요소에는 항목의 시각적 위치를 결정합니다.|  
|조건|선택 사항입니다. 참조 [조건부 특성](../extensibility/vsct-xml-schema-conditional-attributes.md)합니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|부모|필수. 메뉴 또는 항목을 배치할 수를 호스팅하는 그룹입니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[CommandPlacements 요소](../extensibility/commandplacements-element.md)|CommandPlacements 및 CommandPlacement 요소 그룹을 지정합니다.|  
  
## <a name="example"></a>예제  
  
```  
<CommandPlacements>  
  <CommandPlacement guid="guidWidgetPackage" id="cmdidInsertOptions"  
    priority="0x0300">  
    <Parent guid="cmdGuidWidgetCommands" id="menuIDEditWidget"/>  
  </CommandPlacement>  
</CommandPlacements>  
```  
  
## <a name="see-also"></a>참고 항목  
 [CommandPlacements 요소](../extensibility/commandplacements-element.md)   
 [Visual Studio 명령 테이블(.Vsct) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
