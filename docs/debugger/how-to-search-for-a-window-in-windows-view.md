---
title: '방법: 창 뷰에서 창에 대 한 검색 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- windows, searching in Windows view
ms.assetid: 30306970-b861-4315-acf8-f86a43d4e73b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4333a79e76358216ce87697975dcb54173570534
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="how-to-search-for-a-window-in-windows-view"></a>방법: 창 뷰에서 창 검색
특정 창 뷰에서 창에 대 한 검색 조건으로 핸들, 캡션, 클래스 또는 캡션과 클래스의 조합을 사용 하 여 검색할 수 있습니다. 또한 검색의 초기 방향을 지정할 수 있습니다. 대화 상자의 필드에에서는 선택한 창의 특성 창 트리에서 표시 됩니다.  
  
 시작 (모든 windows 데스크톱의 자식), 두 번째 수준으로 확장 트리와 해당 클래스 이름 및 제목으로 데스크톱 수준 창을 식별할 수 있도록 합니다. 바탕 화면 수준 창을 선택 하면 해당 수준 특정 자식 창을 찾을 수를 확장할 수 있습니다.  
  
### <a name="to-search-for-a-window-in-windows-view"></a>창 뷰에서 창 검색 하려면  
  
1.  따라서 정렬 해당 Spy + +는 [창 뷰](../debugger/windows-view.md) 창과 대상 창에 표시 됩니다.  
  
2.  **검색** 메뉴 선택 **창 찾기**합니다.  
  
     [창 경로 대화 상자](../debugger/window-search-dialog-box.md) 열립니다.  
  
    > [!TIP]
    >  화면이 복잡해 선택 된 **Spy 숨기기** 옵션입니다. 이 옵션은 주 Spy + + 창을 숨기고 및 남습니다는 **창 검색** 대화 상자를 다른 응용 프로그램 위에 표시 합니다. Spy + + 주 창을 클릭 하면 복원 되 **확인** 또는 **취소**, 선택을 취소 하면 또는 **Spy + + 숨기기** 옵션입니다.  
  
3.  끌어서는 **찾기 도구** 대상 창 위에 있습니다. 도구를 끌어 놓으면는 **창 검색** 대화 상자는 선택 된 창의 세부 정보를 표시 합니다.  
  
     - 또는  
  
     (예: 디버거)에서 원하는 창 핸들을 알고 있는 경우에 입력할 수 있습니다는 **처리** 상자입니다.  
  
     - 또는  
  
     캡션 및/또는 원하는 창 클래스를 알고 있는 경우에 입력할 수 있습니다는 **캡션** 및 **클래스** 텍스트 상자 및 지우기는 **처리** 입력란.  
  
4.  선택 **를** 또는 **아래로** 검색의 초기 방향에 대 한 합니다.  
  
5.  **확인**을 클릭합니다.  
  
     강조 표시 된 일치 하는 창을 발견 되는 경우는 [창 뷰](../debugger/windows-view.md) 창.