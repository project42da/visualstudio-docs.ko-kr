---
title: 창 속성 대화 상자, 일반 탭 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: reference
helpviewer_keywords:
- Window Properties dialog box, General Tab
ms.assetid: 19142c60-9b32-46ba-a556-b62fd77568c1
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f762d935edab5720ccd9add155dac3d0e5f2f186
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="general-tab-window-properties-dialog-box"></a>창 속성 대화 상자, 일반 탭
사용 하 여는 **일반** 탭을 선택된 된 창에 대 한 정보를 표시 합니다. 표시 하는 [창 속성 대화 상자](../debugger/window-properties-dialog-box.md), 포커스를 이동 하는 [창 뷰](../debugger/windows-view.md) 창. 트리에서 창 노드를 선택한 후 선택 **속성** 에서 **보기** 메뉴.  
  
 다음 설정은에 사용할 수는 **일반** 탭:  
  
|입력|설명|  
|-----------|-----------------|  
|**창 캡션**|창 캡션의 텍스트 또는 텍스트 컨트롤이 면 창에 포함 합니다.|  
|**창 핸들**|이 창의 고유 ID입니다. 창 핸들 번호는 다시 사용 합니다. 해당 창의 사용 기간에만 창을 식별합니다.|  
|**창 프로시저**|이 창에 대 한 창 프로시저 함수의 가상 주소입니다. 이 필드는 또한이 창 유니코드 창 인지와 서브클래싱된 인지를 나타냅니다.|  
|**사각형**|창에 대 한 경계 사각형입니다. 사각형의 크기도 표시 됩니다. 단위는 화면 좌표에서 (픽셀)입니다.|  
|**복원 된 영역**|복원 된 창에 대 한 경계 사각형입니다. 사각형의 크기도 표시 됩니다. 복원 된 영역 창 최대화 되거나 최소화 하는 경우에 사각형에서 달라 집니다. 단위는 화면 좌표에서 (픽셀)입니다.|  
|**클라이언트 영역**|창의 클라이언트 영역에 대 한 경계 사각형입니다. 사각형의 크기도 표시 됩니다. 단위는 창의 클라이언트 영역의 왼쪽 위에 상대적인 픽셀입니다.|  
|**인스턴스 핸들**|응용 프로그램의 인스턴스 핸들입니다. 인스턴스 핸들 고유 하지 않습니다.|  
|**컨트롤 ID 나 메뉴 핸들**|표시 되는 창이 자식 창, 컨트롤 ID 레이블이 표시 됩니다. 컨트롤 ID는이 자식 창의 컨트롤 id입니다. 식별 하는 정수 표시 되 고 창이 한 자식 창에 있지 않으면 메뉴 처리 레이블이 표시 됩니다. 메뉴 핸들은이 창과 연결 된 메뉴의 핸들을 식별 하는 정수입니다.|  
|**사용자 데이터**|이 창 구조에 연결 된 응용 프로그램별 데이터입니다.|  
|**창 바이트**|이 창과 연결 된 추가 바이트의 수입니다. 이러한 접두사 바이트의 의미는 응용 프로그램에 의해 결정 됩니다. 목록 상자 DWORD 형식에서 바이트 값을 보려면 확장 합니다.|