---
title: "단추 요소 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "단추 요소 (VSCT XML 스키마)"
  - "VSCT XML 스키마 요소, 단추"
ms.assetid: 9f2cf94d-dec5-4776-a836-9a89c75f0c87
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# 단추 요소
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

그룹 [단추](../extensibility/button-element.md) 개별 명령을 나타내는 요소입니다.  
  
## 구문  
  
```  
<Buttons>  
  <Button>... </Button>  
  <Button>... </Button>  
</Buttons>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|조건|선택적 요소.[조건부 특성](../extensibility/vsct-xml-schema-conditional-attributes.md)을 참조하세요.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[Buttons Element](../extensibility/buttons-element.md)|단추 요소를 그룹화합니다.|  
|[Button 요소](../extensibility/button-element.md)|사용자 상호 작용할 수 있는 명령을 정의 합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[Commands 요소](../extensibility/commands-element.md)|VSPackage 도구 모음에 있는 명령의 컬렉션을 나타냅니다.|  
  
## 예제  
  
```  
<Buttons> <Button guid="guidMenuAndCommandsCmdSet" id="cmdidMyCommand"     priority="0x100" type="Button"> <Parent guid="guidMenuAndCommandsCmdSet" id="MyMenuGroup"/> <Icon guid="guidGenericCmdBmp" id="bmpArrow"/> <Strings> <ButtonText>C# Command Sample</ButtonText> </Strings> </Button> </Buttons>  
```  
  
## 참고 항목  
 [Vspackage에서 사용자 인터페이스 요소를 추가 하는 방법](../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [명령, 메뉴 및 도구 모음](../extensibility/internals/commands-menus-and-toolbars.md)