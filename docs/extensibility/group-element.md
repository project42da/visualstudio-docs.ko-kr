---
title: "그룹 요소 | Microsoft Docs"
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
ms.assetid: 69faee18-cbf4-470a-b952-c1919c583df8
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# 그룹 요소
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

VSPackage 명령 그룹을 정의합니다.  
  
## 구문  
  
```  
<Group guid="guidMyCommandSet" id="MyGroup" priority="0x101">  
  <Parent>... </Parent>  
</Group>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|guid|필수 요소. GUID\/ID 명령 식별자의 GUID입니다.|  
|ID|필수 요소. ID는 GUID\/ID 명령 식별자입니다.|  
|priority|선택적 요소. 우선 순위를 지정 하는 숫자 값입니다.|  
|조건|선택적 요소.[조건부 특성](../extensibility/vsct-xml-schema-conditional-attributes.md)을 참조하세요.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|부모|선택적 요소. 단추의 부모 요소입니다.|  
|주석|선택적 설명입니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[Groups 요소](../extensibility/groups-element.md)|Vspackage 명령 그룹을 정의 하는 항목을 포함 합니다.|  
  
## 예제  
  
```  
<Group guid="cmdSetGuidWidgetCommands" id="groupIDFileEdit"> <Parent guid="guidSHLMainMenu" id="IDM_VS_TOOL_MAINMENU"/> </Group>  
```  
  
## 참고 항목  
 [Visual Studio 명령 테이블 \(. Vsct\) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)