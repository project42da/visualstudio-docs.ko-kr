---
title: "옵션 페이지 열기 | Microsoft Docs"
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
  - "옵션 페이지 열기"
  - "도구 옵션"
  - "옵션 페이지"
ms.assetid: 6f24cbfa-288a-4a57-831b-bc82587de255
caps.latest.revision: 9
caps.handback.revision: 9
manager: "douge"
---
# 옵션 페이지 열기
패키지 사용자가 설정하는 동안 구성할 수 있도록 옵션 페이지를 프로그래밍 방식으로 표시할 수 있습니다. 패키지가 설치된 후 설정을 변경하기 위해 사용자가 **옵션** 대화 상자를 사용하여 옵션 페이지에 액세스할 수도 있습니다.  
  
### 사용자 지정 옵션 페이지를 표시하려면  
  
1.  옵션 페이지를 만듭니다. 자세한 내용은 [옵션 페이지 만들기](../extensibility/internals/creating-options-pages.md)을 참조하세요.  
  
2.  옵션 페이지를 정의하는 클래스의 이름에 `typeof` 키워드를 적용하여 옵션 페이지의 <xref:System.Type>을 가져옵니다.  
  
3.  옵션 페이지의 <xref:System.Type>을 매개 변수로 사용하여 <xref:Microsoft.VisualStudio.Shell.Package.ShowOptionPage%2A> 메서드를 호출합니다.  
  
     다음 예제에서는 **HelloWorldOptions**라는 옵션 페이지를 표시합니다.  
  
     [!code-cs[UI_UserSettings_ToolsOptionPages#5](../extensibility/internals/codesnippet/CSharp/opening-an-options-page_1.cs)]
     [!code-vb[UI_UserSettings_ToolsOptionPages#5](../extensibility/internals/codesnippet/VisualBasic/opening-an-options-page_1.vb)]  
  
### Visual Studio에서 정의된 옵션 페이지를 표시하려면  
  
1.  레지스트리 하위 키 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\9.0\\ToolsOptionsPages\\에서 표시할 옵션 페이지의 노드를 찾고 해당 GUID\(Page 키 값\)를 복사합니다.  
  
2.  <xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97> 및 <xref:Microsoft.VisualStudio.VSConstants.VSStd97CmdID> 상수가 매개 변수로 포함된 <xref:System.ComponentModel.Design.CommandID> 인스턴스를 만듭니다.  
  
     이를 통해 **옵션** 대화 상자를 지정합니다.  
  
3.  <xref:System.ComponentModel.Design.CommandID> 인스턴스와 GUID 문자열을 매개 변수로 사용하여 <xref:System.ComponentModel.Design.MenuCommandService.GlobalInvoke%2A> 메서드를 호출합니다.  
  
     다음 예제에서는 **텍스트 편집기** 옵션 페이지의 **일반** 탭을 표시합니다.  
  
     [!code-cs[UI_UserSettings_ToolsOptionPages#6](../extensibility/internals/codesnippet/CSharp/opening-an-options-page_2.cs)]
     [!code-vb[UI_UserSettings_ToolsOptionPages#6](../extensibility/internals/codesnippet/VisualBasic/opening-an-options-page_2.vb)]