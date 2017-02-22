---
title: "VisibilityConstraints 요소 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VisibilityConstraints"
helpviewer_keywords: 
  - "VSCT XML 스키마 요소, VisibilityConstraints"
  - "VisibilityConstraints 요소 (VSCT XML 스키마)"
ms.assetid: d6dcd314-6fe4-4693-a189-91fa026c7b34
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# VisibilityConstraints 요소
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

VisibilityConstraints 요소 그룹 명령 및 도구 모음을 정적 표시 여부를 결정 합니다. 표시 여부는 처음에 의해 제어 됩니다는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] VSPackage를 로드 하지 않고 통합된 개발 환경 \(IDE\).  
  
## 구문  
  
```  
<VisibilityConstraints>  
  <VisibilityConstraint>... </VisibilityConstraint>  
  <VisibilityConstraint>... </VisibilityConstraint>  
</VisibilityConstraint>  
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
|[VisibilityItem 요소](../extensibility/visibilityitem-element.md)|명령 및 도구 모음 정적 표시 여부를 결정 합니다.|  
|[VisibilityConstraints](../extensibility/visibilityconstraints-element.md)|명령 및 도구 모음 그룹의 정적 표시 여부를 결정 합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[CommandTable 요소](../extensibility/commandtable-element.md)|VSPackage IDE를 제공 하는 명령 \(예: 메뉴 항목, 메뉴, 도구 모음 및 콤보 상자\)를 나타내는 모든 요소를 정의 합니다.|  
  
## 예제  
  
```  
<VisibilityConstraints> <VisibilityItem guid="cmdSetGuidMyProductCommands"     id="cmdidAddWidget" context="guidNotViewSourceMode"/> </VisibilityConstraints>  
```  
  
## 참고 항목  
 [VisibilityItem 요소](../extensibility/visibilityitem-element.md)   
 [Visual Studio 명령 테이블 \(. Vsct\) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)