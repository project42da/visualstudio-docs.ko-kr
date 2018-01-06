---
title: "명령 처리 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - command handling
ms.assetid: 78f67d92-77f7-45cb-ad75-6e3346379cc3
caps.latest.revision: "20"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 3ecbff62570067b25aae9ad525138687eb281c9f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="command-handling"></a>명령 처리
편집기에는 새 명령을 정의할 수 있습니다. 명령은 도구 모음 또는 상황에 맞는 메뉴에서 메뉴에 일반적으로 표시 됩니다.  
  
 명령 및 메뉴 정의 대 한 자세한 내용은 참조 [명령, 메뉴 및 도구 모음](../extensibility/internals/commands-menus-and-toolbars.md)합니다.  
  
 어떤 상황에 맞는 메뉴를 가로채는 편집기에 표시 됩니다는 언어 서비스를 제어할 수는 <xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID> 열거형입니다. 또는 표식 당 별로 상황에 맞는 메뉴를 제어할 수 있습니다. 자세한 내용은 참조 [언어 서비스 필터에 대 한 중요 한 명령을](../extensibility/internals/important-commands-for-language-service-filters.md)합니다.  
  
## <a name="adding-commands-to-the-editor-context-menu"></a>편집기 상황에 맞는 메뉴에 명령 추가  
 상황에 맞는 메뉴에 명령을 추가 하려면 먼저 특정 그룹에 속하는 메뉴 명령 집합을 정의 해야 합니다. 다음 예제에서는 연습의 일부로 생성 되는.vsct 파일에서 가져온 것 [연습: 추가 기능을 사용자 지정 편집기에](../extensibility/walkthrough-adding-features-to-a-custom-editor.md):  
  
 \<메뉴 guid = "guidCustomEditorCmdSet" id = "IDMX_RTF" 우선 순위 = "0x0000" type = "컨텍스트" >  
  
 \<부모 guid = "guidCustomEditorCmdSet" id = "0" / >  
  
 \<문자열 >  
  
 \<ButtonText > CustomEditor 상황에 맞는 메뉴\</ButtonText >  
  
 \<CommandName > CustomEditorContextMenu\</CommandName >  
  
 \</ 문자열 >  
  
 \</ 메뉴 >  
  
 \</ 메뉴 >  
  
 상황에 맞는 메뉴 명령 텍스트를 추가 하는 위의 텍스트 **CustomEditor 상황에 맞는 메뉴**합니다. 메뉴 GUID는이 편집기를 사용 하 여 만든는 명령 집합의 형식입니다 "컨텍스트"입니다.  
  
 .Vsct 파일에서 정의 해야 하는 필요 하지 않은 미리 정의 된 명령을 사용할 수도 있습니다. 예를 들어 Visual Studio 패키지 템플릿은에서 생성 한 EditorPane.cs 파일을 검사 하면 알게 하는 미리 정의 된 명령 집합을 같은 <xref:Microsoft.VisualStudio.VSConstants.VSStd97CmdID> 정의한 <xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97>, onSelectAll 메서드와 같은 명령 처리기에서 처리 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [명령, 메뉴 및 도구 모음](../extensibility/internals/commands-menus-and-toolbars.md)