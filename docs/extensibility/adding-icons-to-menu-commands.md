---
title: "메뉴 명령에 아이콘 추가 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- icons [Visual Studio], adding to toolbars
- toolbars [Visual Studio], adding icons to commands
- commands [Visual Studio], adding icons
ms.assetid: 362a0c7e-5729-4297-a83f-1aba1a37fd44
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1cdf521228a1878fa94343418bd6a182f9707a2b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="adding-icons-to-menu-commands"></a>메뉴 명령에 아이콘 추가
명령 메뉴 및 도구 모음을 둘 다에 나타날 수 있습니다. 이 도구 모음에서 일반적으로 아이콘 및 텍스트와 함께 표시 되며 명령 아이콘만 (공간을 절약 하려면) 하는 동안 메뉴에 함께 표시 되도록 하려면 명령에 대 한 일반적입니다.  
  
 아이콘은 16 x 16 픽셀 되 고 8 비트 색 농도 (256 색) 또는 32 비트 색 농도 (true 컬러) 일 수 있습니다. 32 비트 컬러 아이콘은 것이 좋습니다. 아이콘은 비트맵을 여러 개 존재할 수 있지만 일반적으로 단일 비트맵의 가로 단일 행으로 정렬 됩니다. 이 비트맵 비트맵에서 사용할 수 있는 개별 아이콘 함께.vsct 파일에서 선언 됩니다. 참조에 대 한 참조는 [비트맵 요소](../extensibility/bitmaps-element.md) 자세한 세부 정보에 대 한 합니다.  
  
## <a name="adding-an-icon-to-a-command"></a>명령 아이콘을 추가합니다.  
 다음 절차는 메뉴 명령 사용 하 여 기존 VSPackage 프로젝트 있다고 가정 합니다. 이 작업을 수행 하는 방법을 알아보려면 참조 [메뉴 명령을 사용 하 여 확장을 만드는](../extensibility/creating-an-extension-with-a-menu-command.md)합니다.  
  
1.  32 비트의 색 농도와 비트맵을 만듭니다. 아이콘은 항상 16 x 16 이므로이 비트맵 16 픽셀 이어야 하 고 16 픽셀 너비의 배수 합니다.  
  
     각 아이콘은 서로 인접 한 행에 비트맵에 배치 됩니다. 알파 채널을 사용 하 여 각 아이콘에 대 한 투명도의 자릿수를 나타냅니다.  
  
     8 비트 색 농도 사용 하는 경우 사용 하 여 자홍, `RGB(255,0,255)`, 투명도로 합니다. 그러나 32 비트 색 아이콘은 기본 설정 합니다.  
  
2.  아이콘 파일 VSPackage 프로젝트에 리소스 디렉터리에 복사 합니다. 솔루션 탐색기에서 프로젝트에 있는 아이콘을 추가 합니다. (리소스를 선택 하 고 상황에 맞는 메뉴에서를 클릭 한 다음 추가, 기존 항목 및 아이콘 파일을 선택 합니다.)  
  
3.  편집기에서.vsct 파일을 엽니다.  
  
4.  추가 `GuidSymbol` 의 이름 가진 요소가 **testIcon**합니다. GUID를 만듭니다 (**도구 / 만들 GUID**을 선택한 후 **레지스트리 형식** 복사를 클릭 하 고)에 붙여 넣을 `value` 특성입니다. 결과 다음과 같이 표시 됩니다.  
  
    ```xml  
    <!-- Create your own GUID -->  
    <GuidSymbol name="testIcon" value="{00000000-0000-0000-0000-0000}">  
    ```  
  
5.  추가 `<IDSymbol>` 아이콘입니다. `name` 특성은 아이콘의 ID 및 `value` 있는 경우의 스트립에서의 위치를 나타냅니다. 단지 하나의 아이콘이 있는 경우 1을 추가 합니다. 결과 다음과 같이 표시 됩니다.  
  
    ```xml  
    <!-- Create your own GUID -->  
    <GuidSymbol name="testIcon" value="{00000000-0000-0000-0000-0000}">  
        <IDSymbol name="testIcon1" value="1" />  
    </GuidSymbol>  
    ```  
  
6.  만들기는 `<Bitmap>` 에 `<Bitmaps>` 아이콘이 들어 있는 비트맵을 나타내기 위해.vsct 파일의 섹션입니다.  
  
    -   설정의 `guid` 값의 이름으로는 `<GuidSymbol>` 이전 단계에서 만든 요소입니다.  
  
    -   설정의 `href` 값 비트맵 파일의 상대 경로입니다 (이 경우 **리소스\\< 아이콘 파일 이름\>**합니다.  
  
    -   설정의 `usedList` 값 앞에서 만든 IDSymbol입니다. 이 특성에는 VSPackage에 사용할 아이콘의 쉼표로 구분 된 목록을 지정 합니다. 목록에 없는 아이콘이는 제외 된 폼을 컴파일하지 않습니다.  
  
         비트맵 블록은 다음과 같이 표시 됩니다.  
  
        ```xml  
        <Bitmap guid="testIcon" href="Resources\<icon file name>" usedList="testIcon1"/>  
        ```  
  
7.  기존 `<Button>` 요소를 설정의 `Icon` 요소 이전에 만든 GUIDSymbol 및 IDSymbol 값입니다. 이 값을 가진 단추 요소의 예는 다음과 같습니다.  
  
    ```xml  
    <Button guid="guidAddIconCmdSet" id="cmdidMyCommand" priority="0x0100" type="Button">  
        <Parent guid="guidAddIconCmdSet" id="MyMenuGroup" />  
        <Icon guid="testIcon" id="testIcon1" />  
        <Strings>  
            <ButtonText>My Command name</ButtonText>  
        </Strings>  
    </Button>  
    ```  
  
8.  프로그램 아이콘을 테스트 합니다. 프로젝트를 빌드하고 디버깅을 시작합니다. 실험적 인스턴스에서 명령을 찾습니다. 추가한 아이콘이 표시 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [확장 메뉴 및 명령](../extensibility/extending-menus-and-commands.md)   
 [VSCT XML 스키마 참조](../extensibility/vsct-xml-schema-reference.md)