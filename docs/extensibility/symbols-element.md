---
title: "기호 요소 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "기호 요소 (VSCT XML 스키마)"
  - "VSCT XML 스키마 요소, 기호"
ms.assetid: 1cda43d8-42a5-4b1b-a3c8-cf0401c3202f
caps.latest.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 7
---
# 기호 요소
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Guid와 다른 VSCT 요소에 의해 사용 되는 Id를 정의 합니다. 비관리 코드에 대 한이 정보 일반적으로 제공 하 여 지정 된 헤더 파일에서 [Extern 요소](../extensibility/extern-element.md)합니다. 코드에서는이 정보를 정의 하는 기호 요소의 자식 요소를 관리 합니다.  
  
 기존.cto 파일에서.vsct 파일을 만들면 기호 기호 요소의 자식으로 생성 됩니다. 자세한 내용은 [방법: 기존 .Cto 파일에서 .Vsct 파일 만들기](../misc/how-to-create-a-dot-vsct-file-from-an-existing-dot-cto-file.md)을 참조하십시오.  
  
 기호 요소와 혼동 해서는 안는 [요소를 정의 합니다.](../extensibility/define-element.md), 전처리기에 의해 사용에 대 한 이름\-값 쌍을 정의 하는 합니다.  
  
## 구문  
  
```  
<Symbols>  
  <GuidSymbol>... </GuidSymbol>  
  <GuidSymbol>... </GuidSymbol>  
</Symbols>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|없음||  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|GuidSymbol|GUID 기호를 정의합니다. GuidSymbol 두 가지 필수 특성인: 이름 및 값입니다. 이름은 기호 이름 및 값이 문자열에서 GUID의 값입니다.<br /><br /> 예: \< GuidSymbol 이름 \= "guidVsPackage1Pkg" value \= "{c5f54698\-101a\-4846\-84d3\-dc748f9cd848}" \/ \>|  
|IDSymbol|기호를 정의합니다. IDSymbol 두 가지 필수 특성인: 이름 및 값입니다. 이름은 기호 이름 및 값의 기호는 문자열의 값입니다.<br /><br /> 예: \< IDSymbol 이름 \= "MyMenuGroup" value \= "0x1020" \/ \>|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[CommandTable 요소](../extensibility/commandtable-element.md)|.Vsct 파일의 루트 요소입니다.|  
  
## 예제  
  
```  
<Symbols> <GuidSymbol name="guidVsPackage1Pkg" value="{c5f54698-101a-4846-84d3-dc748f9cd848}" /> <GuidSymbol name="guidVsPackage1CmdSet" value="{cb9dfd7f-2fcc-4a3e-aae8-f7fe30b1cfac}"> <IDSymbol name="MyMenuGroup" value="0x1020" /> <IDSymbol name="cmdidMyCommand" value="0x0100" /> <IDSymbol name="cmdidMyTool" value="0x0101" /> </GuidSymbol> </Symbols>  
```  
  
## 참고 항목  
 [Visual Studio 명령 테이블 \(. Vsct\) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)