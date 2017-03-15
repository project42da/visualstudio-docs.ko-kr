---
title: "C# 및 C++에서 VSCT 샘플 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "VSCT 파일, 샘플"
ms.assetid: 3218584b-c619-487c-9486-514b04937020
caps.latest.revision: 6
caps.handback.revision: 6
manager: "douge"
---
# C# 및 C++에서 VSCT 샘플
VSCT 명령을 정의 하는 새로운 방법 설정 되어 있습니다.  이 인해 변경 얼마나 VSCT 샘플 C\# 및 c \+ \+에서 컴파일된에서 발생 했습니다.  명령은 이제 외부 파일을 c \+ \+에서 및 C\# 기호 구역에 있는.vsct 파일에 정의 됩니다.  
  
## 명령 정의  
  
### 외부 c \+ \+ 파일  
 C \+ \+ 샘플의 VSCT 컴파일러 명령을 정의 안에서 사용 되는 상수를 정의 하는 외부 파일을 포함 되어 있습니다.  이러한 파일을 포함 하 고 있으므로 명령을 정의에 상수를 정의 하는 방법은 추가 하는 것은 `Extern` 태그를.vsct 파일에 포함 하 고 내부 외부 파일 참조의 이름을 지정은 `href` 특성.  이러한 파일은 다음과 같습니다.  
  
-   Guids.h  
  
-   CommandIDs.h  
  
-   Resources.h  
  
 다음 코드는 c \+ \+.vsct 파일에서 이러한 파일을 포함 하는 방법을 보여 줍니다.  
  
 `<!--This is the file with the definition of the Guids specific for this sample.-->`  
  
 `<Extern href="Guids.h"/>`  
  
 `<!--Definition of the IDs of the commands and VSCT elements specific for this sample.-->`  
  
 `<Extern href="CommandIds.h"/>`  
  
 `<!--Definition of the resources exposed by this package.  Here it is used for the ID of the bitmap.-->`  
  
 `<Extern href="Resource.h"/>`  
  
### C\# 기호  
 C\# 샘플의.vsct 파일에 있는 `Symbols` 절에서 그 명령을 정의할 수 있습니다.  C\#에.vsct 파일에 기호가 정의 명령 테이블에는 Id 요소 정의 방법을에서 기인 합니다.  다음은 명령 및 해당 하는 상수를 지정 합니다. C\#.vsct 파일의 일부입니다.  
  
 `<Symbols>`  
  
 `<!--The first GUID defined here is the one for the package.  It does not contain numeric IDs.-->`  
  
 `<GuidSymbol name="guidMenuAndCommandsPkg" value="{746D5114-B030-4D64-9A6D-E2ABE1E78E56}" />`  
  
 `<!--The GUID for the command set is the one that contains the numeric IDs used in this sample`  
  
 `with the only exception of the one used for the bitmap.-->`  
  
 `<GuidSymbol name="guidMenuAndCommandsCmdSet" value="{10A79DAE-B33C-4FDB-8922-B056628858A1}">`  
  
 `<!--Menus-->`  
  
 `<IDSymbol name="MyToolbar" value="0x101" />`  
  
 `<!--Groups-->`  
  
 `<IDSymbol name="MyMenuGroup" value="0x1010" />`  
  
 `<IDSymbol name="MyToolbarGroup" value="0x1011" />`  
  
 `<IDSymbol name="MyMainToolbarGroup" value="0x1012" />`  
  
 `<IDSymbol name="MyEditorCtxGroup" value="0x1013" />`  
  
 `<!--Commands-->`  
  
 `<IDSymbol name="cmdidMyCommand" value="0x2001" />`  
  
 `<IDSymbol name="cmdidMyGraph" value="0x2002" />`  
  
 `<IDSymbol name="cmdidMyZoom" value="0x2003" />`  
  
 `<IDSymbol name="cmdidDynamicTxt" value="0x2004" />`  
  
 `<IDSymbol name="cmdidDynVisibility1" value="0x2005" />`  
  
 `<IDSymbol name="cmdidDynVisibility2" value="0x2006" />`  
  
 `</GuidSymbol>`  
  
 `<!--Last is the definition of the GUID used for the Bitmap and the ID of its used slots.-->`  
  
 `<GuidSymbol name="guidGenericCmdBmp" value="{0A4C51BD-3239-4370-8869-16E0AE8C0A46}">`  
  
 `<IDSymbol name="bmpArrow" value="1" />`  
  
 `</GuidSymbol>`  
  
 `</Symbols>`  
  
## 비트맵을 포함합니다.  
  
### C\#  
 비트맵 C\# CTO 및 c \+ \+ 이진 파일을 외부 디스크에 저장 됩니다.  정의 비트맵에 대 한 GUID 특성을 제공 합니다 비트맵 id 방식으로 정의 되어 있는 `resID` 특성의 비트맵 및 단추 정의 내부에 사용한 요소의 숫자 id를 포함 하는 비트맵 스트립의 \(`usedList` 특성\).  이 선언문의 중요 한 요소 id 실제 인덱스 \(1부터 시작\)를 비트맵 비트맵 스트립 내는 것입니다.  
  
 다음 예제에서는 비트맵 스트립 포함 된 요소 중 하나만 포함 합니다.  BmpArrow 1로 정의 해야 합니다.이 요소에 대 한 ID Guidmenuandcommandscmdset:bmparrow로 정의 됩니다.  또한 비트맵의 선언입니다.  
  
 `<Bitmap guid="guidGenericCmdBmp" href="GenericCmd.bmp"    usedList="bmpArrow"/>`  
  
## 참고 항목  
 [Visual Studio 명령 테이블 \(. Vsct\) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)