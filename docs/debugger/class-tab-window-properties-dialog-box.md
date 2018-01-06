---
title: "창 속성 대화 상자, 클래스 탭 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords: Window Properties dialog box, Class Tab
ms.assetid: eaec9f07-d580-436d-934d-76c4e59439aa
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: cb10cf8a571d37f27244398e6c957c46cee87f8b
ms.sourcegitcommit: 9e6ff74da1afd8bd2f0e69387ce81f2a74619182
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/04/2018
---
# <a name="class-tab-window-properties-dialog-box"></a>창 속성 대화 상자, 클래스 탭
사용 하 여는 **클래스** 탭을 선택된 된 창 클래스에 대 한 정보가 표시 됩니다. 표시 하는 [창 속성 대화 상자](../debugger/window-properties-dialog-box.md), 포커스를 이동 하는 [창 뷰](../debugger/windows-view.md) 창. 트리에서 창 노드를 선택한 후 선택 **속성** 에서 **보기** 메뉴.  
  
 다음 설정은에 사용할 수는 **클래스** 탭:  
  
|입력|설명|  
|-----------|-----------------|  
|**클래스 이름**|이 창 클래스의 이름 (또는 서 수)입니다.|  
|**클래스 스타일**|클래스 스타일 코드의 조합입니다.|  
|**클래스 바이트**|이 창 클래스와 연결 하는 응용 프로그램별 데이터입니다.|  
|**Atom 클래스**|반환 된 클래스에 대 한 atom는 **RegisterClass** 호출 합니다.|  
|**인스턴스 핸들**|클래스를 등록 하는 모듈의 인스턴스 핸들입니다. 인스턴스 핸들 고유 하지 않습니다.|  
|**창 바이트**|이 클래스의 각 창에 연결 된 추가 바이트의 수입니다. 이러한 접두사 바이트의 의미는 응용 프로그램에 의해 결정 됩니다. 목록 상자 DWORD 형식에서 바이트 값을 보려면 확장 합니다.|  
|**창 프로시저**|현재 주소는 **WndProc** 이 클래스의 창에 대 한 함수입니다. 이 점에서 차이가 **창 프로시저** 에 **일반** 서브클래싱된 하는 경우를 탭 합니다.|  
|**메뉴 이름**|연결 된 windows ("없음" 이면 메뉴 없음)이이 클래스의 주 메뉴의 이름입니다.|  
|**아이콘 핸들**|Windows ("없음" 아이콘이 없을 경우)이이 클래스의 연관 된 아이콘에 대 한 핸들입니다.|  
|**커서 핸들**|Windows ("없음" 커서가 있는 경우)이이 클래스의 연관 된 커서에 대 한 핸들입니다.|  
|**배경 브러시**|이 클래스 또는 ("없음" 된 경우) 창 배경을 칠하는 대 한 미리 정의 된 COLOR_ * 색상 중 하나로 창과 연결 된 배경 브러시에 대 한 핸들입니다.|