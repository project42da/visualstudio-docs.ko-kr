---
title: "How to: Search for a Window in Windows View | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "windows, searching in Windows view"
ms.assetid: 30306970-b861-4315-acf8-f86a43d4e73b
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# How to: Search for a Window in Windows View
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

핸들, 캡션, 클래스 또는 캡션과 클래스의 조합을 검색 조건으로 사용하여 창 뷰에서 특정 창을 검색할 수 있으며,  검색의 초기 방향을 지정할 수도 있습니다.  이 대화 상자의 필드에는 창 트리에서 선택한 창의 특성이 표시됩니다.  
  
 클래스 이름과 제목으로 데스크톱 수준 창을 식별할 수 있도록 두 번째 수준\(데스크톱의 자식인 모든 창\)까지 확장된 상태에서 트리를 시작합니다.  데스크톱 수준 창을 선택한 후에는 이 수준을 확장하여 특정 자식 창을 찾을 수 있습니다.  
  
### 창 뷰에서 창을 검색하려면  
  
1.  [창 뷰](../debugger/windows-view.md) 창인 Spy\+\+와 대상 창이 보이도록 창을 정렬합니다.  
  
2.  **검색** 메뉴에서 **창 찾기**를 선택합니다.  
  
     [창 검색 대화 상자](../debugger/window-search-dialog-box.md)가 열립니다.  
  
    > [!TIP]
    >  화면을 간결하게 만들려면 **Spy 숨기기** 옵션을 선택합니다.  이 옵션은 Spy\+\+의 주 창을 숨기고 **창 검색** 대화 상자만 다른 응용 프로그램 위에 표시된 상태로 둡니다.  **확인** 또는 **취소**를 클릭하거나 **Spy\+\+ 숨기기** 옵션의 선택을 취소하면 Spy\+\+의 주 창이 복원됩니다.  
  
3.  **찾기 도구**를 대상 창 위로 끌어 옵니다.  이 도구를 끌어 올 때 **창 검색** 대화 상자에는 선택된 창의 세부 내용이 표시됩니다.  
  
     – 또는 –  
  
     원하는 창의 핸들\(예를 들면 디버거에서 복사됨\)을 알고 있으면 **핸들** 상자에 이 핸들을 입력할 수 있습니다.  
  
     – 또는 –  
  
     원하는 창의 캡션 및\/또는 클래스를 알고 있으면 **캡션**과 **클래스** 텍스트 상자에 각각 캡션과 텍스트를 입력하고 **핸들** 텍스트 상자를 지웁니다.  
  
4.  검색의 초기 방향으로 **위로** 또는 **아래로**를 선택합니다.  
  
5.  **확인**을 클릭합니다.  
  
     일치하는 창이 발견되면 [창 뷰](../debugger/windows-view.md) 창에서 강조 표시됩니다.