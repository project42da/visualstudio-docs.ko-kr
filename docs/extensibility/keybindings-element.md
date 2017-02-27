---
title: "키 바인딩 요소 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "KeyBindings"
helpviewer_keywords: 
  - "VSCT XML 스키마 요소, 키 바인딩"
  - "키 바인딩 요소 (VSCT XML 스키마)"
ms.assetid: 26a15d5c-ddea-4977-af7f-d795ff09c7ad
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# 키 바인딩 요소
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

키 바인딩 요소와 다른 키 바인딩 그룹화 키 바인딩 요소를 그룹화합니다.  
  
## 구문  
  
```  
<KeyBindings>  
  <KeyBinding>... </KeyBinding>  
  <KeyBinding>... </KeyBinding>  
</KeyBindings>  
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
|[키 바인딩 요소](../extensibility/keybinding-element.md)|명령에 대 한 바로 가기 키를 지정합니다.|  
|[KeyBindings](../extensibility/keybindings-element.md)|키 바인딩 요소 그룹 및 다른 키 바인딩 그룹화 합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[CommandTable 요소](../extensibility/commandtable-element.md)|명령을 나타내는 모든 요소를 정의 합니다.|  
  
## 예제  
  
```  
<KeyBindings> <KeyBinding guid="guidWidgetPackage" id="cmdidUpdateWidget" editor="guidWidgetEditor" key1="VK_F5"/> <KeyBinding guid="guidWidgetPackage" id="cmdidRunWidget" editor="guidWidgetEditor" key1="VK_F5" mod1="Control"/> </KeyBindings>  
```  
  
## 참고 항목  
 [키 바인딩 요소](../extensibility/keybinding-element.md)   
 [Visual Studio 명령 테이블 \(. Vsct\) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)