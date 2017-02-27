---
title: "IDSymbol 요소 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDSymbol 요소 (VSCT XML 스키마)"
  - "VSCT XML 스키마 요소, IDSymbol"
ms.assetid: 760cfd20-3c06-422c-9103-98bfa1f387f8
caps.latest.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 7
---
# IDSymbol 요소
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

`IDSymbol` 요소 메뉴, 그룹 또는 명령을 나타내는 GUID:ID 쌍의 ID를 포함 합니다. 부모 개체에서 제공 되는 GUID `GuidSymbol` 요소입니다.`IDSymbol` 요소에는 `name` 특성에 포함 되어 있는 ID에 대 한 이름을 제공 하는 `value` 특성입니다.  
  
## 구문  
  
```  
<IDSymbol name=ElementName value="0x0010" />  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|name|필수 요소. 이름 ID 기호입니다.|  
|값|필수 요소. ID 기호가의 숫자 ID 값입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[GuidSymbol 요소](../extensibility/guidsymbol-element.md)|메뉴, 그룹 또는 명령을 나타내는 GUID:ID 쌍의 GUID를 포함 합니다.`IDSymbol` 요소를 그룹화합니다.|  
  
## 설명  
 모든 `IDSymbol` 요소에는 주어진 `GuidSymbol` 요소는 고유 해야 합니다. `value`합니다. 그러나 `IDSymbol` 동일한 값을 가진 요소가 패키지 서로 다른 부모를가지고 있을 수 있습니다.  
  
## 참고 항목  
 [Visual Studio 명령 테이블 \(. Vsct\) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)