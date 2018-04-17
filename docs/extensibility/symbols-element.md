---
title: 요소를 기호 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Symbols element (VSCT XML schema)
- VSCT XML schema elements, Symbols
ms.assetid: 1cda43d8-42a5-4b1b-a3c8-cf0401c3202f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 87e9159e1e392ff242407b105589f4f33341b45b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="symbols-element"></a>기호 요소
Guid 및 다른 VSCT 요소에 의해 사용 되는 Id를 정의 합니다. 비관리 코드에 대 한이 정보는 일반적으로 제공 하 여 지정 된 헤더 파일에서 [Extern 요소](../extensibility/extern-element.md)합니다. 코드에서는이 정보를 정의 하는 기호 요소의 자식 요소를 관리 합니다.  
  
 기존.cto 파일에서.vsct 파일을 만드는 경우 기호가 기호 요소의 자식으로 생성 됩니다. 자세한 내용은 참조 [하는 방법: 만들기는 합니다. 기존 Vsct 파일입니다. Cto 파일](../extensibility/internals/how-to-create-a-dot-vsct-file.md#how-to-create-a-dot-vsct-file-from-an-existing-dot-cto-file)합니다.  
  
 기호 요소와 일치 하지 않습니다는 [요소 정의](../extensibility/define-element.md), 전처리기에서 사용 하기 위해 이름-값 쌍을 정의 하는 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
<Symbols>  
  <GuidSymbol>... </GuidSymbol>  
  <GuidSymbol>... </GuidSymbol>  
</Symbols>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|없음||  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|GuidSymbol|GUID 기호를 정의합니다. GuidSymbol에 두 개의 필수 특성이: 이름 및 값입니다. 이름은 기호 이름 및 값은 문자열에서 GUID의 값입니다.<br /><br /> 예를 들어:\<GuidSymbol 이름 = "guidVsPackage1Pkg" value = "{c5f54698-101a-4846-84d3-dc748f9cd848을 (를)" / >|  
|IDSymbol|기호를 정의합니다. IDSymbol에 두 개의 필수 특성이: 이름 및 값입니다. 이름은 기호 이름 및 값을 문자열로 기호 값은입니다.<br /><br /> 예를 들어:\<IDSymbol 이름 = "MyMenuGroup" value = "0x1020" / >|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[CommandTable 요소](../extensibility/commandtable-element.md)|.Vsct 파일의 루트 요소입니다.|  
  
## <a name="example"></a>예제  
  
```  
<Symbols>  
  <GuidSymbol name="guidVsPackage1Pkg" value="{c5f54698-101a-4846-84d3-dc748f9cd848}" />  
  <GuidSymbol name="guidVsPackage1CmdSet" value="{cb9dfd7f-2fcc-4a3e-aae8-f7fe30b1cfac}">  
    <IDSymbol name="MyMenuGroup" value="0x1020" />  
    <IDSymbol name="cmdidMyCommand" value="0x0100" />  
    <IDSymbol name="cmdidMyTool" value="0x0101" />  
  </GuidSymbol>  
</Symbols>  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio 명령 테이블(.Vsct) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)