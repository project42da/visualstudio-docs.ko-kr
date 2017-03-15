---
title: "요소를 포함 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Include"
helpviewer_keywords: 
  - "요소 (VSCT XML 스키마)를 포함 합니다."
  - "VSCT XML 스키마 요소를 포함"
ms.assetid: c923dfe6-084a-4105-aec1-f0a3f8399c54
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# 요소를 포함 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

찾을 수 있는 파일을 지정 하는 Include 요소에 제공 된 현재 파일에 대 한 경로 포함 합니다.  모든 기호 및 정의 된 형식은 컴파일된 결과에 포함 됩니다.  
  
## 구문  
  
```c#  
<Include href="stdidcmd.h" />  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|href|필수 요소. 헤더 파일의 경로:<br /><br /> href\="stdidcmd.h"|  
|조건|선택적 요소.[조건부 특성](../extensibility/vsct-xml-schema-conditional-attributes.md)을 참조하세요.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|없음|없음|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[CommandTable 요소](../extensibility/commandtable-element.md)|모든 명령을 나타내는 요소 정의\-메뉴 항목, 메뉴, 도구 모음 및 콤보 상자 즉,\-VSPackage IDE를 제공 하는 합니다.|  
  
## 예제  
  
```  
<Include href="PackagePlacements.vsct"/>  
```  
  
## 참고 항목  
 [Visual Studio 명령 테이블 \(. Vsct\) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)