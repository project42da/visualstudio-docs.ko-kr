---
title: "GuidSymbol 요소 | Microsoft Docs"
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
  - "VSCT XML 스키마 요소, GuidSymbol"
  - "GuidSymbol 요소 (VSCT XML 스키마)"
ms.assetid: 11fb3545-8974-4776-9a54-6b6e7739ae31
caps.latest.revision: 8
caps.handback.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
---
# GuidSymbol 요소
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

`GuidSymbol` 요소 메뉴, 그룹 또는 명령을 나타내는 GUID:ID 쌍의 GUID를 포함 합니다. 제공 되는 ID는 `IDSymbol` 요소에는 `GuidSymbol` 요소입니다.`GuidSymbol` 요소에는 `name` 특성에 포함 된 GUID에 대 한 알기 쉬운 이름을 지정 하는 `value` 특성입니다.  
  
## 구문  
  
```  
<GuidSymbol name="guidMyCommandSet" value="{xxxxxxxxxxxxx-xxxx-xxxx-xxxxxxxxxxxx}">  
  <IDSymbol>... </IDSymbol>  
  <IDSymbol>... </IDSymbol>  
</GuidSymbol>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|name|필수 요소. GUID 기호와의 이름입니다.|  
|값|필수 요소. GUID 기호와의 GUID입니다.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[IDSymbol 요소](../extensibility/idsymbol-element.md)|메뉴, 그룹 또는 명령을 나타내는 GUID:ID 쌍의 ID를 포함 합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[기호 요소](../extensibility/symbols-element.md)|그룹 `GuidSymbol` .vsct 파일의 요소입니다.|  
  
## 설명  
 일반적으로.vsct 파일에 포함 된 3 개의 `GuidSymbol` 요소에 해당 `Symbols` 패키지 자체, 단추 및 기타 시각적 구성 요소에 대 한 아이콘을 제공 하는 비트맵에 대 한 개와 명령 집합 \(메뉴, 그룹 및 명령을 사용할 수 있도록 패키지의 컬렉션\)에 대 한 하나에 대 한 섹션입니다. 모든 `IDSymbol` 요소에는 주어진 `GuidSymbol` 요소는 고유 해야 합니다. `value`합니다. 그러나 `IDSymbol` 동일한 값을 가진 요소가 패키지 서로 다른 부모를가지고 있을 수 있습니다.  
  
## 참고 항목  
 [Visual Studio 명령 테이블 \(. Vsct\) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)