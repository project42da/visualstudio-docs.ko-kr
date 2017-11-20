---
title: "처리 속성 대화 상자, 일반 탭 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Process properties for Windows NT
ms.assetid: 86f4d61d-a594-4aac-8960-c5279b4a10fd
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c9548b35d893fa08458c6254776c8949cc83c510
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="general-tab-process-properties-dialog-box"></a>프로세스 속성 대화 상자, 일반 탭
사용 하 여는 **일반** 특정 프로세스에 대 한 자세한 내용을 탭 합니다. 표시 하는 [프로세스 속성 대화 상자](../debugger/process-properties-dialog-box.md), 포커스를 이동 하는 [프로세스 뷰](../debugger/processes-view.md) 창. 트리에서 프로세스 노드를 선택한 후 선택 **속성** 에서 **보기** 메뉴.  
  
 다음 설정은에 사용할 수는 **일반** 탭:  
  
|입력|설명|  
|-----------|-----------------|  
|**모듈 이름**|모듈의 이름입니다.|  
|**프로세스 ID**|이 프로세스의 고유 ID입니다. 프로세스 ID 번호는 계속 사용 되므로 프로세스의 수명에 대 한 프로세스를 식별 합니다. 프로세스 개체 유형은 프로그램이 실행 될 때 생성 됩니다. 프로세스의 모든 스레드는 같은 주소 공간을 공유 하 고 동일한 데이터에 대 한 액세스 권한이.|  
|**기본 우선 순위**|이 프로세스의 현재 기본 우선 순위입니다. 스레드는 프로세스 내에서 발생 하 고 프로세스의 기본 우선 순위를 기준으로 자신의 기본 우선 순위를 낮출 수 있습니다.|  
|**스레드**|이 프로세스에서 현재 활성 상태인 스레드 수입니다.|  
|**CPU 시간**|이 프로세스와 해당 스레드에서 소요 된 총 CPU 시간입니다. 권한 있는 시간을 더한 사용자 시간을과 같습니다.|  
|**사용자 시간**|이 프로세스의이 스레드가 사용자 모드로 실행 중인 코드를 비 유휴 스레드를 소비 했습니다 누적 경과 시간입니다. 응용 프로그램 창 관리자, 그래픽 엔진 등 하위 시스템과 사용자 모드에서 실행 합니다.|  
|**시스템된 시간**|총 경과 시간이이 프로세스를 실행 특권 모드에서 비 유휴 스레드에서입니다. 서비스 계층, 실행 루틴 및 커널 특권 모드에서 실행 됩니다. 그래픽 어댑터와 프린터 이외의 대부분의 장치에 대 한 장치 드라이버를 특권 모드에서 실행할 수도 있습니다. Windows 응용 프로그램에 대해 수행 하는 일부 작업은 시스템 시간 및 다른 하위 시스템 프로세스에서 나타날 수 있습니다.|  
|**경과 시간**|이 프로세스를 실행 하는 총 경과 시간입니다.|