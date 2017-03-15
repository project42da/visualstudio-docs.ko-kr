---
title: "요소를 정의 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "VSCT XML 스키마 요소 정의"
  - "요소 (VSCT XML 스키마)를 정의 합니다."
ms.assetid: 5aee74e3-de41-4dc6-9618-93e158af56dd
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# 요소를 정의 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

기호 이름 및 값 쌍을 정의합니다. 이 기호는 조건부 특성으로 평가할 수 있습니다. 자세한 내용은 [조건부 특성](../extensibility/vsct-xml-schema-conditional-attributes.md)을 참조하십시오. 참고 항목에서 [기호 요소](../extensibility/symbols-element.md)합니다.  
  
## 구문  
  
```  
<Define name="Mode" value="Standard" />  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|name|필수 요소. 기호 이름:<br /><br /> 이름 \= "모드"|  
|값|필수 요소. 기호 값:<br /><br /> 값 \= "Standard"|  
|조건|선택적 요소. 자세한 내용은 [조건부 특성](../extensibility/vsct-xml-schema-conditional-attributes.md)을 참조하세요.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[CommandTable 요소](../extensibility/commandtable-element.md)|통합된 개발 환경 \(IDE\)에 VSPackage를 제공 하는 명령을 나타내는 모든 요소를 정의 합니다. 예를 들어 메뉴 항목, 메뉴, 도구 모음 및 콤보 상자입니다.|  
  
## 예제  
  
```  
<Define name="DEMO_UI"/> <Define name="MODE" value="Standard"/>  
```  
  
## 참고 항목  
 [Visual Studio 명령 테이블 \(. Vsct\) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)