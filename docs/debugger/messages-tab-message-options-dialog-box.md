---
title: 메시지 옵션 대화 상자, 메시지 탭 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: reference
helpviewer_keywords:
- message options, Messages
ms.assetid: fb9fa211-e82c-40a5-9e4b-ba8de07313c0
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f19da533d2ab13e7493eae53af8dea3af4e520df
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="messages-tab-message-options-dialog-box"></a>메시지 옵션 대화 상자, 메시지 탭
사용 하 여는 **메시지** 탭에 표시할 메시지 형식을 선택 하려면 [메시지 뷰](../debugger/messages-view.md), 및 메시지 검색 조건을 지정 하려면. 표시 하는 [메시지 옵션 대화 상자](../debugger/message-options-dialog-box.md), 선택 **로그 메시지** 에서 **Spy** 메뉴.  
  
 일반적으로 처음 선택 하면 **메시지 그룹**, 한 다음 개별 선택 하 여 선택 영역을 미세 조정할 **보기로 메시지**합니다. **모든** 모든 메시지 유형을 선택 하는 단추와 **None** 단추 형식 선택을 모두 취소 합니다.  
  
 다음 설정은에 사용할 수는 **메시지** 탭:  
  
 **메시지 보기**  
 보기에 대 한 특정 메시지를 선택 합니다. 새 메시지 창을 만들 모든 메시지를 표시할 수 있습니다. 메시지를 필터링 하는 경우는 **메시지** 탭에서 해당 필터는 새 메시지를 창 뷰에 이미 표시 되어 있는 메시지가 없는에 적용 됩니다.  
  
 **메시지 그룹**  
 표시할 메시지 그룹을 선택 합니다. 사용 가능한 그룹은 다음과 같습니다.  
  
-   WM_USER: 코드로 WM_USER 보다 크거나 같은 경우  
  
-   등록: 등록 된는 **RegisterWindowMessage** 호출  
  
-   범위는 0 (WM_USER-1)에서 알 수 없는 메시지를 알 수 없음:  
  
 이러한 **메시지 그룹** 아래의 특정 항목에 매핑되지 않는 **표시할 메시지**합니다. 그룹을 선택 하는 경우에 선택 메시지 스트림에 직접 적용 됩니다.  
  
 내에서 회색으로 표시 확인란 **메시지 그룹** 나타냅니다는 **표시할 메시지** 목록 상자에 해당 그룹의 메시지에 대해 수정한; 해당 그룹의 메시지 유형 중 일부만 선택 됩니다.  
  
 **설정을 기본값으로 저장**  
 메시지 검색 옵션으로 나중에 사용에 대 한 현재 설정을 저장 합니다. 이러한 설정은 Spy + +를 끝낼 때에 저장 됩니다.