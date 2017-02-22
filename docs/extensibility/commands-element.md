---
title: "Commands 요소 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Commands"
helpviewer_keywords: 
  - "Commands 요소 (VSCT XML 스키마)"
  - "VSCT XML 스키마 요소를 명령"
ms.assetid: 47cf16a5-d78b-452e-86f6-b5893856dddf
caps.latest.revision: 17
caps.handback.revision: 17
ms.author: "gregvanl"
manager: "ghogen"
---
# Commands 요소
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

VSPackage 도구 모음에 있는 명령의 컬렉션을 나타냅니다. 컬렉션 최대 5 개의 하위 섹션을 다음과 같이 있을 수 있습니다: 메뉴, 그룹, 단추, 바로 가기 단축키 \+, 및 비트맵입니다.  
  
 각 하위 섹션 자식 요소, 예를 들어 \< 메뉴 \> 인 고유한 명령 ID를 GUID와 숫자 식별자 쌍으로 식별 됩니다. GUID "명령 집합"을 식별 하 고 논리적으로 관련 된 명령을 그룹화 하는 데 사용 됩니다. VSPackage 다른 Vspackage에 정의 된 명령 Id와 충돌 하지 않도록 설정 하는 자체 명령을 정의 해야 합니다.  
  
## 구문  
  
```  
<Commands package="GuidMyPackage" >  
  <Menus>... </Menus>  
  <Groups>... </Groups>  
  <Buttons>... </Buttons>  
  <Combos>... </Combos>  
  <Bitmaps>... </Bitmaps>  
</Commands>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|패키지|명령을 제공 하 여 VSPackage를 식별 하는 GUID입니다.<br /><br /> 예를 들어 패키지 \= "guidVsPackage1Pkg"입니다.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[메뉴 요소](../extensibility/menus-element.md)|VSPackage를 구현 하는 모든 메뉴를 정의 합니다.|  
|[Groups 요소](../extensibility/groups-element.md)|VSPackage에서 명령 그룹을 정의 하는 항목을 포함 합니다.|  
|[단추 요소](../extensibility/buttons-element.md)|단추 요소를 그룹화합니다.|  
|[비트맵 요소](../extensibility/bitmaps-element.md)|비트맵 요소를 그룹화합니다.|  
|[바로 가기 단축키 \+ 요소](../extensibility/combos-element.md)|콤보 요소를 그룹화합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[CommandTable 요소](../extensibility/commandtable-element.md)|VSPackage IDE를 제공 하는 명령을 나타내는 모든 요소를 정의 합니다. 가능한 요소는 메뉴 항목, 메뉴, 도구 모음 및 콤보 상자.|  
  
## 예제  
 다음 예제를 사용 하는 방법을 보여 줍니다는 [Commands Element](../extensibility/commands-element.md)합니다.  
  
```  
<Commands package="guidMyPackage"> <Menus> <Menu Condition="'%(DEBUG)' != 'true'" guid="cmdSetGuidMyProductCommands" id="menuIDMainMenu" priority="0x0000" type="Menu"> <Annotation> <Documentation>this is an annotation</Documentation> <AppInfo> <CustomData> <CustomSubElement>Some data</CustomSubElement> </CustomData> </AppInfo> </Annotation> <CommandFlag>AlwaysCreate</CommandFlag> <Strings> <ButtonText>MainMenu</ButtonText> </Strings> </Menu> </Menus> <Commands>  
```  
  
## 참고 항목  
 [Vspackage에서 사용자 인터페이스 요소를 추가 하는 방법](../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [명령, 메뉴 및 도구 모음](../extensibility/internals/commands-menus-and-toolbars.md)