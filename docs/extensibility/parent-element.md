---
title: "부모 요소 | Microsoft Docs"
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
  - "VSCT XML 스키마 요소를 부모"
  - "부모 요소 (VSCT XML 스키마)"
ms.assetid: e4624ac8-1b9a-4940-910a-528a661cefad
caps.latest.revision: 8
caps.handback.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
---
# 부모 요소
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

단추 또는 콤보 상자의 부모 그룹 수만 있습니다. 메뉴 또는 그룹의 부모 메뉴 또는 그룹 수 있습니다. 에 [CommandPlacement 요소](../extensibility/commandplacement-element.md), 이 요소는 필요에 다른 모든 경우에 선택 사항입니다. 이 요소를 생략 하면의 부모 `Group_Undefined:0` 암시 됩니다.  
  
## 구문  
  
```  
<Parent guid="guidMyCommandSet" id="MyParentGroupOrMenu" />  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|guid|필수 요소. GUID의 GUID\/ID 명령 식별자입니다.|  
|ID|필수 요소. ID의 GUID\/ID 명령 식별자입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[CommandTable 요소](../extensibility/commandtable-element.md)|통합된 개발 환경 \(IDE\)에 VSPackage를 제공 하는 명령을 나타내는 모든 요소를 정의 합니다. 예를 들어 메뉴 항목, 메뉴, 도구 모음 및 콤보 상자입니다.|  
|[단추 요소](../extensibility/buttons-element.md)|[Button 요소](../extensibility/button-element.md) 요소를 그룹화합니다.|  
|[메뉴 요소](../extensibility/menus-element.md)|VSPackage를 구현 하는 모든 메뉴를 정의 합니다.|  
|[Groups 요소](../extensibility/groups-element.md)|Vspackage 명령 그룹을 정의 하는 항목을 포함 합니다.|  
  
## 참고 항목  
 [Visual Studio 명령 테이블 \(. Vsct\) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)