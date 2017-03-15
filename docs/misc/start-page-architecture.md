---
title: "시작 페이지 아키텍처 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "시작 페이지 아키텍처"
  - "시작 페이지 xaml"
ms.assetid: f94afe27-0be3-47d9-8e17-b0fd429017bd
caps.latest.revision: 9
caps.handback.revision: 9
manager: "douge"
---
# 시작 페이지 아키텍처
이 문서 Visual Studio 포함 된 시작 페이지 도구 창의의 아키텍처를 설명 합니다.  추가 하거나 내부 구조를 변경 하지 않고 시작 페이지의 항목을 변경 하려면이 정보를 사용할 수 있습니다.  
  
 Visual Studio 시작 페이지 Windows Presentation Foundation \(WPF\) 확장 응용 프로그램 피드백 언어 \(XAML에서\) 기록 됩니다.  XAML 태그에 대 한 자세한 내용은 [XAML 개요\(WPF\)](../Topic/XAML%20Overview%20\(WPF\).md).  
  
## 페이지 구조  
 시작 페이지로 구성 되어 있는 <xref:System.Windows.Controls.Image> 요소와 두 <xref:System.Windows.Controls.Grid> 최상위 수준에 요소가 `Grid` 요소.  `Image` 요소가 도구 창의 위쪽을 표시 하 고 Visual Studio 로고를 포함 합니다.  아래 로고를 왼쪽 `Grid` 요소가 들어 있는 명령 단추를 새 프로젝트에 대 한의  **최근에 사용한 프로젝트** 목록 및 시작 페이지 옵션에 대 한 영역입니다.  오른쪽 `Grid` 요소를 포함 한 <xref:System.Windows.Controls.TabControl> 요소는  **신청** 탭을는  **지침 및 리소스** 탭을 하는  **최신 뉴스** 탭.  왼쪽 및 오른쪽 사이의 중앙 열 정의 된 `Grid` 요소를 있지만 해당 컨텐츠가 없습니다 및 공백으로만 사용 됩니다.  
  
### 창의 본문  
 배경 도구 창의 최상위 수준으로 표시 됩니다 `Grid` 요소입니다.  기본 열 너비에 여기서 정의 되는 `ColumnDefinitions` 요소입니다.  로고 이미지의 높이 설정에서 `RowDefinitions` 요소입니다.  
  
 행 정 및 열 정의 배열에 저장 됩니다.  모눈에 요소를 배치 하도록 설정의 `Grid.Column` 및 `Grid.Row` 특성에 해당 하는 인덱스와 일치 하도록 <xref:System.Windows.Controls.ColumnDefinition> 및 <xref:System.Windows.Controls.RowDefinition> 요소입니다.  
  
### 로고 이미지  
 Visual Studio 로고 최상위 표의 맨 위 행을 차지 \(`Grid.Row="0"`\)으로 `Image` 요소입니다.  차례로 다른 이미지를 표시 하는 `Source` 특성에는 `Image` 요소에 서로 다른 이미지 파일.  이미지를 제거 하려면 삭제는 `Image` 요소와 집합의 `height` 해당 특성이 최상위 `RowDefinition` 요소에 `0` 표 맨 위 행을 숨기려면 \(0\).  
  
### 왼쪽된 열  
 시작 페이지의 왼쪽된 열에 표시 됩니다 있는 `Grid` 에 `Grid.Column="0"` 및 `Grid.Row="1"`.  명령 단추 구분선에서 최근에 사용한 프로젝트 격자를 호스트 하는 세 개의 행에 대 한 정의가이 요소를 포함 하는 `StackPanel` Visual Studio 옵션을 표시 하는 요소입니다.  
  
 기존 행의 하나에 추가 하거나 새 행 정의 추가 하 여이 모눈에 요소를 추가할 수 있습니다.  새 행을 정의 하는 경우 증가 합니다 기억의 `Grid.Row` 아래에서 새 행에 표시 된 요소의 값입니다.  
  
### 가운데 열  
 가운데 열 공백 한 요소가 들어 있습니다.  가운데 열에 있는 요소를 추가 하는 위치 `Grid.Column="1"` 및 `Grid.Row="1"`.  조정 되었는지 확인을 `Width` 특성 열 정의 변경할 수 있도록 합니다.  
  
### 오른쪽 열  
 오른쪽 열이 포함 된 `Grid` 요소에 `Grid.Column="1"` 및 `Grid.Row="1"`.  표를 포함 한 `TabControl` 세 개의 탭으로 구성 요소입니다.  
  
 추가 하 여 탭을 추가 <xref:System.Windows.Controls.TabItem> 요소를 탭 컨트롤에 표시 된 대로 [연습: 시작 페이지 사용자 지정 XAML에 추가](../extensibility/walkthrough-adding-custom-xaml-to-the-start-page.md), 또는 편집 하거나 기존 탭을 제거할 수 있습니다.  탭이 나타나는 왼쪽에 위쪽 아래쪽 태그에 나타난 대로 오른쪽 같은 순서로 사용자 인터페이스 \(UI\)입니다.  
  
 오른쪽 열의 눈금 탭 컨트롤 외부에 요소를 추가 하는 경우 새 행 또는 열 모눈에 예상 대로 나타나는지 확인 합니다 정의 하는 것이 좋습니다.  
  
## 참고 항목  
 [시작 페이지 사용자 지정](../ide/customizing-the-start-page-for-visual-studio.md)   
 [시작 페이지 모범 사례](../misc/start-page-best-practices.md)   
 [사용자 지정 시작 페이지를 배포합니다.](../extensibility/deploying-custom-start-pages.md)