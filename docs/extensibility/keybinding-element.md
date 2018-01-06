---
title: "KeyBinding 요소 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VSCT XML schema elements, KeyBindings
- KeyBinding element (VSCT XML schema)
ms.assetid: e55a1098-15df-42a9-9f87-e3a99cf437dd
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 2019a34e55148007cd75df12212bd4b0a897159c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="keybinding-element"></a>KeyBinding 요소
키 바인딩 요소는 명령에 대 한 바로 가기 키를 지정합니다.  
  
 명령은 연결 된 단일 및 이중 키 바인딩을 가질 수 있습니다. 단일 키 바인딩이의 예로 CTRL + S에 대 한는 **저장** 명령입니다. 이중 키 바인딩을 두 개의 연속 키 조합의 명령을 트리거할 필요 합니다. 이중 키 바인딩이 예로 CTRL + K, CTRL + K를 책갈피를 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
<Keybinding guid="MyGuid" id="MyId" Editor="MyEditor" key1="B" key2="x" mod1="Control" mod2="Alt" />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|guid|필수.|  
|ID|필수.|  
|편집기|필수. GUID 편집기는이 바로 가기 키 활성화 될 편집 컨텍스트를 나타냅니다. 전역 바인딩 범위 값은 "guidVSStd97"입니다.|  
|key1|필수. 유효한 값은 모두 입력할 수 영숫자 및 두 자리 16 진수 값 0x로 시작 하 고 [VK_constants](https://msdn.microsoft.com/en-us/library/windows/desktop/dd375731.aspx)합니다.|  
|mod1|선택 사항입니다. 어떠한 조합의 CTRL, ALT 및 SHIFT 공백으로 구분 합니다.|  
|key2|선택 사항입니다. 유효한 값은 모두 입력할 수 영숫자 및 두 자리 16 진수 값 0x로 시작 하 고 [VK_constants](https://msdn.microsoft.com/en-us/library/windows/desktop/dd375731.aspx)합니다.|  
|mod2|선택 사항입니다. 어떠한 조합의 CTRL, ALT 및 SHIFT 공백으로 구분 합니다.|  
|에뮬레이터|선택 사항입니다.|  
|조건|선택 사항입니다. 참조 [조건부 특성](../extensibility/vsct-xml-schema-conditional-attributes.md)합니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|부모||  
|주석||  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[KeyBindings 요소](../extensibility/keybindings-element.md)|그룹 키 바인딩 요소와 다른 KeyBindings 그룹화 합니다.|  
  
## <a name="example"></a>예  
  
```  
<KeyBindings>  
  <KeyBinding guid="guidWidgetPackage" id="cmdidUpdateWidget"   
    editor="guidWidgetEditor" key1="VK_F5"/>  
  <KeyBinding guid="guidWidgetPackage" id="cmdidRunWidget"   
    editor="guidWidgetEditor" key1="VK_F5" mod1="Control"/>  
</KeyBindings>  
```  
  
## <a name="see-also"></a>참고 항목  
 [KeyBindings 요소](../extensibility/keybindings-element.md)   
 [Visual Studio 명령 테이블(.Vsct) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
