---
title: "색, 그라데이션 및 불투명도 설정 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "UI 요소 디자인[Visual Studio SDK]"
ms.assetid: 1734bdc7-5e16-46c7-8507-eef5cea75cb9
caps.latest.revision: 31
caps.handback.revision: 31
manager: "douge"
---
# 색, 그라데이션 및 불투명도 설정
Visual Studio의 모든 UI\(사용자 인터페이스\) 요소는 WPF\(Windows Presentation Foundation\)에서 만들어집니다. 따라서 도구 창 또는 기타 UI 요소를 만들 때 해당 요소에 적절한 특성을 설정하여 색, 그라데이션 및 불투명도를 적용할 수 있습니다.**속성** 창을 사용하여 특정 값으로 설정하거나 IDE\(통합 개발 환경\)에 시스템 값을 쿼리할 수 있습니다. 확장을 IDE의 나머지 부분과 비슷하게 설정하려면 시스템 값을 사용하는 것이 좋습니다.  
  
 Windows Forms UI 및 네이티브 코드 UI는 이전 버전과의 호환성을 위해 계속 지원됩니다. 비 WPF 확장에서 색 및 그라데이션을 설정하는 방법에 대한 자세한 내용은 [!INCLUDE[vs_orcas_long](../debugger/includes/vs_orcas_long_md.md)] 설명서를 참조하세요.  
  
## 색, 그라데이션 및 불투명도 설정  
 `Background`, `Foreground`, `Opacity` 또는 기타 시각적 특성을 설정하여 대부분 XAML 요소의 모양을 변경할 수 있습니다. 이러한 특성은 <xref:System.Windows.Media.Brush?displayProperty=fullName>를 값으로 사용하는 속성에 해당합니다.  
  
#### 도구 창에서 배경 색, 그라데이션 및 불투명도를 설정하려면  
  
1.  MyControl.xaml을 엽니다.  
  
2.  **XAML** 창의 최상위 수준 <xref:System.Windows.Controls.UserControl> 요소에서 `background=`를 입력합니다.  
  
     IntelliSense에 BackGround 특성에 대한 색 목록이 표시됩니다.  
  
     목록에서 색을 선택합니다.  
  
3.  **속성** 창에서 **브러시** 노드를 확장한 다음 **배경**을 클릭합니다.  
  
     **속성** 창에 색 선택이 표시됩니다. 색 선택 위에는 브러시를 나타내는 아이콘 행이 표시됩니다.  
  
4.  슬라이더를 사용하여 색을 선택합니다.  
  
     XAML이 즉시 업데이트되어 새 배경색이 표시됩니다.  
  
5.  그라데이션 브러시 아이콘을 클릭합니다.  
  
     색 선택이 그라데이션 선택기로 변경됩니다.  
  
6.  슬라이더를 사용하여 그라데이션을 선택합니다.  
  
     XAML이 즉시 업데이트되어 새 배경 그라데이션이 표시됩니다.  
  
7.  이미지 브러시 아이콘을 클릭합니다.  
  
     그라데이션 선택이 이미지 선택 도구로 변경됩니다.  
  
8.  이미지를 선택하고 해당 늘이기 및 타일 매개 변수를 설정합니다.  
  
     XAML이 즉시 업데이트되어 새 배경 이미지가 표시됩니다.  
  
9. Null 브러시 아이콘을 클릭합니다.  
  
     디자이너의 배경이 중립으로 돌아오고 `BackGround` 특성이 `"{x:Null}"`로 설정됩니다.  
  
## 시스템 값 쿼리  
 Visual Studio의 다른 부분에 설정된 브러시를 참조하는 <xref:Microsoft.VisualStudio.Shell.VsBrushes?displayProperty=fullName> 클래스 속성을 사용하여 시스템 값을 쿼리할 수 있습니다.  
  
#### 시스템 값을 쿼리하여 색, 그라데이션 및 불투명도를 설정하려면  
  
1.  XAML 요소를 선택합니다.  
  
2.  다음 예제에서처럼 요소 정의에서 요소의 시각적 개체 특성 중 하나를 `VsBrushes` 클래스의 속성으로 설정합니다.  
  
     [!CODE [TWShortcutMenu#32](../CodeSnippet/VS_Snippets_VSSDK/twshortcutmenu#32)]  
  
     [DynamicResource](../Topic/DynamicResource%20Markup%20Extension.md) 확장을 사용하면 필요에 따라\(예: 사용자가 설정을 변경할 때\) 값을 변경할 수 있습니다.`VsBrushes` 클래스는 기본 WPF 네임스페이스의 일부가 아니므로 [x:Static](../Topic/x:Static%20Markup%20Extension.md) 확장을 사용해야 합니다.  
  
## 참고 항목  
 [도구 창 확장](../misc/extending-tool-windows.md)