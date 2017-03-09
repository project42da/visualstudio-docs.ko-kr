---
title: "도구 창 확장 | Microsoft Docs"
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
  - "창[Visual Studio SDK], 도구"
  - "문서 창"
  - "도구 창"
  - "창[Visual Studio SDK], 문서"
ms.assetid: 252f7b99-b44a-4a63-88d9-3a0ca48ac4f1
caps.latest.revision: 37
caps.handback.revision: 37
manager: "douge"
---
# 도구 창 확장
Visual Studio 도구 창은 일반적으로 파일 기반이 아닌 읽기 전용 창입니다. 이런 점에서 파일을 읽기\/쓰기 모드로 표시하는 문서 창과는 다릅니다.**도구 상자**, **솔루션 탐색기**, **속성** 창 및 **웹 브라우저**는 도구 창의 예입니다.  
  
 Visual Studio 2010 이상 버전의 모든 도구 창은 WPF 기반입니다. Visual Studio 2010 이전의 Visual Studio 버전에서는 도구 창이 Windows Forms 기반이었습니다. Windows Forms 기반 창은 계속 표시될 수 있지만 새 도구 창은 WPF 기반이어야 합니다.  
  
## 도구 창 필수  
 도구 창을 제공하려면 Visual Studio에 등록하고 기본 크기 및 위치를 지정해야 합니다. 자세한 내용은 [레지스트리에 도구 창](../extensibility/tool-windows-in-the-registry.md)을 참조하세요.  
  
 도구 창은 일반적으로 메뉴 명령을 클릭하여 만들거나 엽니다. 도구 창을 프로그래밍 방식으로 만들려면 [프로그래밍 방식으로 도구 창 열기](../misc/opening-a-tool-window-programmatically.md)를 참조하세요.  
  
 도구 창은 기본적으로 단일 인스턴스입니다. 즉, 도구 창의 인스턴스를 한 번에 하나만 열 수 있습니다. 단일 인스턴스 도구 창이 열린 후 IDE를 닫을 때까지 열린 상태로 유지됩니다. 단일 인스턴스 도구 창에서 닫기 단추를 클릭하면 표시 유형만 변경됩니다. 창의 여러 인스턴스가 동시에 열릴 수 있도록 다중 인스턴스 도구 창도 만들 수 있습니다. 자세한 내용은 [다중 인스턴스 도구 창 만들기](../extensibility/creating-a-multi-instance-tool-window.md)를 참조하세요.  
  
 도구 창을 문서 프레임에서 도킹, 부동 또는 탭할 수 있습니다. 도구 창 프레임이 IDE에서 제공되고 크기, 위치, 도킹 상태 및 기타 영구적 속성을 제어하는 데 사용됩니다. 도구 창에서 내용을 표시합니다. 기본 크기 및 위치는 도구 창이 처음 열릴 때만 적용되고 이후에는 도구 창 상태가 유지됩니다.  
  
 도구 창에서 WPF 사용자 컨트롤을 호스트하고 도구 모음을 지원할 수 있습니다.<xref:Microsoft.VisualStudio.Shell.WindowPane.Window%2A> 속성을 재정의하여 호스트된 컨트롤의 핸들을 반환할 수 있습니다.  
  
 도구 창은 *동적*일 수 있습니다\(*자동 표시*라고도 함\). 관련된 UI 컨텍스트가 적용될 때마다 동적 도구 창이 표시됩니다. 자동 표시를 사용하면 IDE에서 창의 혼잡함을 줄일 수 있습니다. 자세한 내용은 [동적 도구 창 열기](../extensibility/opening-a-dynamic-tool-window.md)을 참조하세요.  
  
 VSPackage가 도구 창을 만드는 유일한 방법은 아닙니다. 추가 기능에서 Visual Studio 자동화 모델을 사용하여 도구 창을 만들 수 있습니다. 자세한 내용은 [How to: Create and Control Tool Windows](../Topic/How%20to:%20Create%20and%20Control%20Tool%20Windows.md)을 참조하세요.  
  
## 참고 항목  
 [Tool Windows](../misc/extending-tool-windows.md)   
 [문서 창](../extensibility/internals/document-windows.md)   
 [도구 창에 검색 추가](../extensibility/adding-search-to-a-tool-window.md)