---
title: "Extern 요소 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Extern"
helpviewer_keywords: 
  - "Extern VSCT XML 스키마 요소"
  - "Extern 요소 (VSCT XML 스키마)"
ms.assetid: db6c3ddd-a1ba-450a-897a-bb568a5377fc
caps.latest.revision: 15
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 15
---
# Extern 요소
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Extern 요소는 컴파일 타임에.vsct 파일 병합할 모든 외부 헤더 \(.h\) 파일을 참조 합니다. VSCT 컴파일러에 지정 하거나 참조 하 여 Include 경로에 파일을 병합할 수 있어야는 [요소를 포함 합니다.](../extensibility/include-element.md)합니다. 다른.vsct 파일 또는 c \+ \+ 헤더 파일의 파일 수 있습니다.  
  
 헤더 파일에 정의 된 형식 이어야 합니다 "\#define \[기호\] \[값\]" 값은 이전에 정의 된 경우 다른 기호를 수 있습니다. 정의 명령 항목의 조건문에 사용할 수 있습니다. 실제로 사용 되는 모든 기호는 삭제 됩니다.  
  
 CommandTable Element  
Extern Element  
  
## 구문  
  
```  
<Extern href="stdidcmd.h" />  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|href|필수 요소. 헤더 파일의 경로:<br /><br /> href\="stdidcmd.h"|  
|조건|선택적 요소.[조건부 특성](../extensibility/vsct-xml-schema-conditional-attributes.md)을 참조하세요.|  
|language|선택적 요소. 모든 기본 언어 [\< 문자열 \>](../extensibility/strings-element.md) 명령 테이블에 있는 요소:<br /><br /> language \= "en\-us"|  
  
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
<?xml version="1.0" encoding="utf-8"?> <CommandTable xmlns="http://schemas.microsoft.com/VisualStudio/2005-10- 18/CommandTable" xmlns:xs="http://www.w3.org/2001/XMLSchema"> <Extern href="C:\VSCore\vscommon\inc\vsshlids.h"/> … <Commands package="guidMyPackage"> </CommandTable>  
```  
  
## 참고 항목  
 [Visual Studio 명령 테이블 \(. Vsct\) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)   
 [Vspackage에서 사용자 인터페이스 요소를 추가 하는 방법](../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [명령, 메뉴 및 도구 모음](../extensibility/internals/commands-menus-and-toolbars.md)