---
title: "VSCT XML 스키마 참조 | Microsoft Docs"
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
  - "Visual Studio 명령 테이블 구성 파일 (VSCT), XML 스키마"
  - "VSCT XML 스키마 요소"
ms.assetid: 49e7efae-e713-4762-a824-96fdaf92cdc9
caps.latest.revision: 14
caps.handback.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
---
# VSCT XML 스키마 참조
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

각 요소와 특성 명령 테이블 컴파일러 스키마 요소의 테이블 허용 되는 자식으로 제공합니다.  
  
 XML 기반 명령 테이블 구성 \(.vsct\) 파일 통합된 개발 환경 \(IDE\)에 VSPackage를 제공 하는 명령 요소를 정의 합니다. 이러한 요소는 메뉴 항목, 메뉴, 도구 모음 및 콤보 상자에 포함 됩니다.  
  
> [!NOTE]
>  VSCT 컴파일러.vsct 파일에는 전처리기를 실행할 수 있습니다. 이 일반적으로 하기 때문에 c \+ \+ 파일에 사용 되는 구문과 동일한 구문이 있는 매크로 및 c \+ \+ 전처리기에 정의할 수 있습니다 포함 됩니다. 이 작업의 예는.vsct에 제공 됩니다 파일에 **새 프로젝트** VSPackage 프로젝트에 대 한 마법사를 만듭니다.  
  
## 선택적 요소  
 일부 VSCT 요소는 선택적입니다. 경우에 `Parent` 인수가 지정 되지 않은, Group\_Undefined:0 암시 됩니다. 하는 경우는 `Icon` 인수가 지정 되지 않은, guidOfficeIcon:msotcidNoIcon 암시 됩니다. 바로 가기 키가 정의 하는 경우 에뮬레이션을 일반적으로 사용 되지 않습니다, 선택 사항입니다.  
  
 비트맵 항목에서 비트맵 스트립의 위치를 지정 하 여 컴파일 타임에 포함 될 수는 `href` 인수입니다. 비트맵 스트립 DLL의 리소스에서 추출 되지 않고 병합 중에 복사 됩니다. 때는 `href` 인수가 제공 되는 `usedList` 인수, 선택적 되며 모든 슬롯 비트맵 스트립에 사용 되는 것으로 간주 됩니다.  
  
 기호화 된 이름을 사용 하 여 모든 GUID 및 ID 값을 정의 되어야 합니다. 이러한 이름은 VSCT \< 기호 \> 섹션 또는 헤더 파일에 정의할 수 있습니다. 심볼 이름은 \< 포함 \> 요소를 포함 하거나 \< Extern \> 요소에 의해 참조 로컬 이어야 합니다. 심볼 이름의 간단한 패턴을 따를 경우 \< Extern \> 요소에 지정 된 헤더 파일에서 가져온 \#define 기호 값입니다. 값으로 해당 기호 이전에 정의 된 다른 기호를 수 있습니다. OLE 또는 c \+ \+ 형식 GUID 정의 따라야 합니다. ID 값은 다음 줄에 표시 된 대로 10 진수 또는 16 진수 0 x가 앞에 수 있습니다.  
  
-   {6D484634\-E53D\-4a2c\-ADCB\-55145C9362C8}  
  
-   {0x6d484634, 0xe53d, 0x4a2c, {0xad, 0xcb, 0x55, 0x14, 0x5c, 0x93, 0x62, 0xc8}}  
  
 XML 주석을 사용 될 수 있지만 왕복 그래픽 사용자 인터페이스 \(GUI\) 도구를 삭제할 수 있습니다. \< 주석 \> 요소의 콘텐츠 형식에 관계 없이 유지 보장 됩니다.  
  
## 스키마 계층 구조  
 .Vsct 파일에 다음과 같은 주요 요소가 있습니다.  
  
 [CommandTable 요소](../extensibility/commandtable-element.md)  
  
 [Extern 요소](../extensibility/extern-element.md)  
  
 [요소를 포함 합니다.](../extensibility/include-element.md)  
  
 [요소를 정의 합니다.](../extensibility/define-element.md)  
  
 [Commands 요소](../extensibility/commands-element.md)  
  
 [CommandPlacements 요소](../extensibility/commandplacements-element.md)  
  
 [VisibilityConstraints 요소](../extensibility/visibilityconstraints-element.md)  
  
 [키 바인딩 요소](../extensibility/keybindings-element.md)  
  
 [UsedCommands 요소](../extensibility/usedcommands-element.md)  
  
 [부모 요소](../extensibility/parent-element.md)  
  
 [Icon 요소](../extensibility/icon-element.md)  
  
 [문자열 요소](../extensibility/strings-element.md)  
  
 [명령 플래그 요소](../extensibility/command-flag-element.md)  
  
 [기호 요소](../extensibility/symbols-element.md)  
  
 [조건부 특성](../extensibility/vsct-xml-schema-conditional-attributes.md)  
  
## 참고 항목  
 [Vspackage에서 사용자 인터페이스 요소를 추가 하는 방법](../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Vspackage의 명령 라우팅](../extensibility/internals/command-routing-in-vspackages.md)