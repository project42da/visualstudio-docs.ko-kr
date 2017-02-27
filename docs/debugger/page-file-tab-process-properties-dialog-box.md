---
title: "프로세스 속성 대화 상자, 페이지 파일 탭 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Windows NT의 프로세스 속성"
ms.assetid: daf41a06-8a55-48f6-95f5-49a8416bd308
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# 프로세스 속성 대화 상자, 페이지 파일 탭
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

**페이지 파일** 탭을 사용하여 프로세스의 페이징 파일을 검사할 수 있습니다.  [프로세스 속성 대화 상자](../debugger/process-properties-dialog-box.md)를 표시하려면 포커스를 [프로세스 뷰](../debugger/processes-view.md) 창으로 이동합니다.  그런 다음 트리에서 프로세스 노드를 선택하고 **보기** 메뉴에서 **속성**을 선택합니다.  
  
 **페이지 파일** 탭에서 사용할 수 있는 설정은 다음과 같습니다.  
  
|Entry|설명|  
|-----------|--------|  
|**페이지 파일 바이트**|이 프로세스가 페이징 파일에서 사용하고 있는 현재 페이지 수입니다.  페이징 파일에는 프로세스에 의해 사용되지만 다른 파일에 포함되지 않은 데이터의 페이지가 저장됩니다.  페이징 파일은 모든 프로세스에 의해 사용되므로 다른 프로세스가 실행 중인 동안 페이징 파일의 공간이 부족하면 오류가 발생할 수 있습니다.|  
|**최고 페이지 파일 바이트**|이 프로세스가 페이징 파일에서 사용한 최대 페이지 수입니다.|  
|**페이지 폴트**|이 프로세스에서 실행 중인 스레드에 의해 발생한 페이지 폴트 수입니다.  페이지 폴트는 스레드가 주 메모리에 있는 해당 작업 집합에 없는 가상 메모리 페이지를 참조하는 경우에 발생합니다.  따라서 페이지가 대기 목록에 있어 주 메모리에 이미 로드된 경우 또는 페이지가 다른 공유 프로세스에 의해 사용되고 있는 경우에는 페이지가 검색되지 않습니다.|