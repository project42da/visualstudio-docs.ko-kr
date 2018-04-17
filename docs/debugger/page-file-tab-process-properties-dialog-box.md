---
title: 프로세스 속성 대화 상자, 페이지 파일 탭 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: reference
helpviewer_keywords:
- Process properties for Windows NT
ms.assetid: daf41a06-8a55-48f6-95f5-49a8416bd308
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1c5a0b5b498eacab4f53471530f51f8c59aed25e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="page-file-tab-process-properties-dialog-box"></a>프로세스 속성 대화 상자, 페이지 파일 탭
사용 하 여는 **페이지 파일** 프로세스의 페이징 파일을 검사 하는 탭 합니다. 표시 하는 [프로세스 속성 대화 상자](../debugger/process-properties-dialog-box.md), 포커스를 이동 하는 [프로세스 뷰](../debugger/processes-view.md) 창. 트리에서 프로세스 노드를 선택한 후 선택 **속성** 에서 **보기** 메뉴.  
  
 다음 설정은에 사용할 수는 **페이지 파일** 탭:  
  
|입력|설명|  
|-----------|-----------------|  
|**페이지 파일 바이트**|이 프로세스에서 페이징 파일에 사용 하는 페이지의 현재 수입니다. 페이징 파일에 프로세스에서 사용 되지만 다른 파일에 포함 되지 데이터 페이지를 저장 합니다. 페이징 파일은 모든 프로세스에서 사용 하 고 다른 프로세스에서 실행 하는 동안 페이징 파일의 공간 부족 오류가 발생할 수 있습니다.|  
|**최고 페이지 파일 바이트**|페이징 파일에이 프로세스에서 사용한 페이지의 최대 수입니다.|  
|**페이지 폴트**|이 프로세스에서 실행 중인 스레드가 페이지 폴트 수입니다. 페이지 폴트의 주 메모리 작업 집합에 없는 가상 메모리 페이지를 참조할 때 발생 합니다. 따라서 페이지 검색 되지 것입니다 디스크에서 대기 목록에 있으면 및이 따른 주 메모리에 이미 있는 페이지를 공유 하거나 다른에 의해 사용 되는 경우 처리 합니다.|