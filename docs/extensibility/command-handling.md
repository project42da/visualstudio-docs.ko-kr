---
title: "명령 처리 | Microsoft Docs"
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
  - "편집기 [Visual Studio SDK] 레거시-명령 처리"
ms.assetid: 78f67d92-77f7-45cb-ad75-6e3346379cc3
caps.latest.revision: 20
caps.handback.revision: 20
ms.author: "gregvanl"
manager: "ghogen"
---
# 명령 처리
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

편집기 새 명령을 정의할 수 있습니다. 명령이 메뉴에서 도구 모음 또는 상황에 맞는 메뉴에서 일반적으로 표시 됩니다.  
  
 명령 및 메뉴를 정의 하는 방법에 대 한 자세한 내용은 참조 [명령, 메뉴 및 도구 모음](../extensibility/internals/commands-menus-and-toolbars.md)합니다.  
  
 어떤 상황에 맞는 메뉴를 해석 하 여 편집기에 표시 됩니다 언어 서비스를 제어할 수는 <xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID> 열거형입니다. 또는 표식 당 기준에 맞는 메뉴를 제어할 수 있습니다. 자세한 내용은 참조 [언어 서비스 필터에 대 한 중요 한 명령](../extensibility/internals/important-commands-for-language-service-filters.md)합니다.  
  
## <a name="adding-commands-to-the-editor-context-menu"></a>편집기 상황에 맞는 메뉴에 명령 추가  
 상황에 맞는 메뉴에 명령을 추가 하려면 먼저 특정 그룹에 속하는 메뉴 명령 집합을 정의 해야 합니다. 다음 예제는 자습서의 일부로 생성 되는.vsct 파일에서 가져온 [연습: 추가 기능을 사용자 지정 편집기로](../extensibility/walkthrough-adding-features-to-a-custom-editor.md):  
  
 \< 메뉴 guid = "guidCustomEditorCmdSet" id = "IDMX_RTF" 우선 순위 = "0x0000" type = "컨텍스트">  
  
 \< 부모 guid = "guidCustomEditorCmdSet" id = "0" />  
  
 \< 문자열>  
  
 \<를 로드 합니다>CustomEditor 상황에 맞는 메뉴 \< /를 로드 합니다>  
  
 \< CommandName>CustomEditorContextMenu \< / CommandName>  
  
 \< 문자열 />  
  
 \< / 메뉴>  
  
 \< / 메뉴>  
  
 위 텍스트는 상황에 맞는 메뉴 명령 텍스트와 함께 추가 **CustomEditor 상황에 맞는 메뉴**합니다. 메뉴 GUID는이 편집기를 사용 하 여 만든 명령 집합의 형식은 "컨텍스트"입니다.  
  
 .Vsct 파일에 정의 해야 하는 필요 하지 않은 미리 정의 된 명령을 사용할 수도 있습니다. 예를 들어 Visual Studio 패키지 템플릿에 의해 생성 되는 EditorPane.cs 파일을 검사 하면 알 수는 미리 정의 된 명령 집합을 같은 <xref:Microsoft.VisualStudio.VSConstants.VSStd97CmdID> 정의한 <xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97>, onSelectAll 메서드와 같은 명령 처리기에서 처리 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [명령, 메뉴 및 도구 모음](../extensibility/internals/commands-menus-and-toolbars.md)