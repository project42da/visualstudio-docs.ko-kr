---
title: "UsedCommands 요소 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "UsedCommands"
helpviewer_keywords: 
  - "UsedCommands 요소 (VSCT XML 스키마)"
  - "VSCT XML 스키마 요소, UsedCommands"
ms.assetid: 5e000ee0-a919-46e9-9277-2a0659f1eb78
caps.latest.revision: 13
caps.handback.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
---
# UsedCommands 요소
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

UsedCommand 요소와 다른 UsedCommands 그룹화 UsedCommands 요소를 그룹화합니다.  
  
 UsedCommands 요소는 선택 사항입니다. 패키지 외부에 정의 된 명령을 호출 하지 않으면.vsct 파일에이 섹션을 포함할 필요가 없습니다.  
  
## 구문  
  
```  
<UsedCommands condition="Defined(DEBUG)">  
  <UsedCommand ... />  
</UsedCommands>  
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
|[UsedCommand 요소](../extensibility/usedcommand-element.md)|다른 코드에 의해 구현 되는 명령입니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[CommandTable 요소](../extensibility/commandtable-element.md)|통합된 개발 환경 \(IDE\)에 VSPackage 제공 하는 명령 \(예: 메뉴 항목, 메뉴, 도구 모음 및 콤보 상자\)를 나타내는 모든 요소를 정의 합니다.|  
  
## 예제  
  
```  
<UsedCommands> <UsedCommand guid="guidVSStd97" id="cmdidCut"/> <UsedCommand guid="guidVSStd97" id="cmdidCopy"/> <UsedCommand guid="guidVSStd97" id="cmdidPaste"/> </UsedCommands>  
```  
  
## 참고 항목  
 [UsedCommand 요소](../extensibility/usedcommand-element.md)   
 [Visual Studio 명령 테이블 \(. Vsct\) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)