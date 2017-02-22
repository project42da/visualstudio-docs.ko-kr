---
title: "메시지 옵션 대화 상자, 메시지 탭 | Microsoft Docs"
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
  - "메시지 옵션, 메시지"
ms.assetid: fb9fa211-e82c-40a5-9e4b-ba8de07313c0
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 메시지 옵션 대화 상자, 메시지 탭
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

**메시지** 탭을 사용하여 [메시지 뷰](../debugger/messages-view.md)에 표시할 메시지 형식을 선택하고 메시지 검색 조건을 지정할 수 있습니다.  [메시지 옵션 대화 상자](../debugger/message-options-dialog-box.md)를 표시하려면 **Spy** 메뉴에서 **로그 메시지**를 선택합니다.  
  
 일반적으로 먼저 **메시지 그룹**을 선택한 다음 개별 **표시할 메시지**를 선택하여 선택 내용을 세부적으로 조정합니다.  **모두** 단추를 클릭하면 모든 메시지 형식이 선택되고 **없음** 단추를 클릭하면 모든 메시지 형식이 선택 취소됩니다.  
  
 **메시지** 탭에서 사용할 수 있는 설정은 다음과 같습니다.  
  
 **표시할 메시지**  
 표시할 특정 메시지를 선택합니다.  새 메시지 창을 만들면 이 창에 모든 메시지를 표시할 수 있습니다.  **메시지** 탭에서 메시지를 필터링하는 경우 새 메시지에만 필터가 적용되고 창 뷰에 이미 표시되어 있는 메시지에는 필터가 적용되지 않습니다.  
  
 **메시지 그룹**  
 표시할 메시지 그룹을 선택합니다.  다음과 같은 그룹을 사용할 수 있습니다.  
  
-   WM\_USER: WM\_USER보다 크거나 같은 코드가 있는 그룹  
  
-   등록: **RegisterWindowMessage** 호출로 등록된 그룹  
  
-   알 수 없음: 0에서 \(WM\_USER – 1\) 사이의 범위에 있는 알 수 없는 메시지  
  
 이러한 **메시지 그룹**은 **표시할 메시지** 아래의 특정 항목으로 매핑되지 않습니다.  그룹을 선택하면 선택된 그룹이 메시지 스트림에 직접 적용됩니다.  
  
 **메시지 그룹** 내의 회색 확인란은 **표시할 메시지** 목록 상자가 해당 그룹에 있는 메시지에 대해 수정되었고 이 그룹에 있는 일부 메시지 형식이 선택되지 않았음을 나타냅니다.  
  
 **설정을 기본값으로 저장**  
 현재 설정을 나중에 사용하기 위해 메시지 검색 옵션으로 저장합니다.  이러한 설정은 Spy\+\+를 종료할 때도 저장됩니다.