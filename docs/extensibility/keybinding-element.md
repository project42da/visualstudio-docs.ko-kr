---
title: "키 바인딩 요소 | Microsoft Docs"
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
  - "VSCT XML 스키마 요소, 키 바인딩"
  - "키 바인딩 요소 (VSCT XML 스키마)"
ms.assetid: e55a1098-15df-42a9-9f87-e3a99cf437dd
caps.latest.revision: 12
caps.handback.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
---
# 키 바인딩 요소
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

키 바인딩 요소는 명령에 대 한 바로 가기 키를 지정합니다.  
  
 명령에는 연결 된 단일 및 이중 키 바인딩 있을 수 있습니다. 단일 키 바인딩의 예는 CTRL \+ S는 **저장** 명령입니다. 이중 키 바인딩을 두 개의 연속 된 키 조합의 명령을 트리거할 필요 합니다. 이중 키 바인딩의 예는 CTRL \+ K,CTRL \+ K를 책갈피를 설정 합니다.  
  
## 구문  
  
```  
<Keybinding guid="MyGuid" id="MyId" Editor="MyEditor" key1="B" key2="x" mod1="Control" mod2="Alt" />  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|guid|필수 요소.|  
|ID|필수 요소.|  
|편집기|필수 요소. GUID 편집기 바로 가기 활성화 될 편집 컨텍스트를 나타냅니다. 전역 바인딩 범위 값은 "guidVSStd97"입니다.|  
|k e y 1|필수 요소. 유효한 값은 모든 입력할 수 영숫자도 앞에 0 x와 VK\_constants 두 자리 16 진수 값입니다.|  
|mod1|선택적 요소. CTRL, ALT 및 공백으로 구분 하는 shift 키의 모든 조합입니다.|  
|k e y 2|선택적 요소. 유효한 값은 모든 입력할 수 영숫자도 앞에 0 x와 VK\_constants 두 자리 16 진수 값입니다.|  
|mod2|선택적 요소. CTRL, ALT 및 공백으로 구분 하는 shift 키의 모든 조합입니다.|  
|에뮬레이터|선택적 요소.|  
|조건|선택적 요소.[조건부 특성](../extensibility/vsct-xml-schema-conditional-attributes.md)을 참조하세요.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|부모||  
|주석||  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[키 바인딩 요소](../extensibility/keybindings-element.md)|키 바인딩 요소 그룹 및 다른 키 바인딩 그룹화 합니다.|  
  
## 예제  
  
```  
<KeyBindings> <KeyBinding guid="guidWidgetPackage" id="cmdidUpdateWidget" editor="guidWidgetEditor" key1="VK_F5"/> <KeyBinding guid="guidWidgetPackage" id="cmdidRunWidget" editor="guidWidgetEditor" key1="VK_F5" mod1="Control"/> </KeyBindings>  
```  
  
## 참고 항목  
 [키 바인딩 요소](../extensibility/keybindings-element.md)   
 [Visual Studio 명령 테이블 \(. Vsct\) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)