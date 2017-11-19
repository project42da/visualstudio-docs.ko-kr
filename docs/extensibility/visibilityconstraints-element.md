---
title: "VisibilityConstraints 요소 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VisibilityConstraints
helpviewer_keywords:
- VSCT XML schema elements, VisibilityConstraints
- VisibilityConstraints element (VSCT XML schema)
ms.assetid: d6dcd314-6fe4-4693-a189-91fa026c7b34
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f26268e6168379632868c07a9d9c58f9485c8ada
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="visibilityconstraints-element"></a>VisibilityConstraints 요소
VisibilityConstraints 요소 명령 및 도구 모음 그룹의 정적 표시 여부를 결정 합니다. 에 의해 표시 유형을 제어 먼저 됩니다는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] VSPackage를 로드 하지 않고 통합된 개발 환경 (IDE).  
  
## <a name="syntax"></a>구문  
  
```  
<VisibilityConstraints>  
  <VisibilityConstraint>... </VisibilityConstraint>  
  <VisibilityConstraint>... </VisibilityConstraint>  
</VisibilityConstraint>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|조건|선택 사항입니다. 참조 [조건부 특성](../extensibility/vsct-xml-schema-conditional-attributes.md)합니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[VisibilityItem 요소](../extensibility/visibilityitem-element.md)|명령 및 도구 모음 정적 표시 여부를 결정 합니다.|  
|[VisibilityConstraints](../extensibility/visibilityconstraints-element.md)|명령 및 도구 모음 그룹의 정적 표시 여부를 결정 합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[CommandTable 요소](../extensibility/commandtable-element.md)|IDE에 VSPackage를 제공 하는 명령 (예: 메뉴 항목, 메뉴, 도구 모음 및 콤보 상자)을 나타내는 모든 요소를 정의 합니다.|  
  
## <a name="example"></a>예제  
  
```  
<VisibilityConstraints>  
  <VisibilityItem guid="cmdSetGuidMyProductCommands"     id="cmdidAddWidget"  
    context="guidNotViewSourceMode"/>  
</VisibilityConstraints>  
```  
  
## <a name="see-also"></a>참고 항목  
 [VisibilityItem 요소](../extensibility/visibilityitem-element.md)   
 [Visual Studio 명령 테이블(.Vsct) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)