---
title: "개체 수명 뷰 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.performance.view.objectlifetime"
helpviewer_keywords: 
  - "수명, 개체"
  - "개체 수명 뷰"
  - "성능 보고서, 개체 수명 뷰"
  - "프로파일링 도구 보고서, 수명 뷰"
  - "프로파일링 도구, 수명 뷰"
ms.assetid: d0501fdd-4b3a-4e74-b6ac-51d950a2e15b
caps.latest.revision: 24
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 24
---
# 개체 수명 뷰
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

개체 수명 뷰는 성능 세션 속성 페이지에서 **추가적으로 .NET 개체 수명 정보 수집**을 선택한 경우에 사용할 수 있습니다.  
  
 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 가비지 수집기는 응용 프로그램의 메모리 할당 및 해제를 관리합니다.  가비지 수집기의 성능을 최적화하기 위해 관리되는 힙은 0세대, 1세대 및 2세대의 3개 세대로 나뉩니다.  런타임 가비지 수집기는 새 개체를 0세대에 저장합니다.  수집 후에도 남아 있는 개체는 수준이 올라가 1세대와 2세대에 저장됩니다.  
  
 가비지 수집기는 전체 개체 세대의 할당을 해제하여 메모리를 회수합니다.  프로파일링된 응용 프로그램에서 만든 개체의 경우 개체 수명 뷰에 해당 개체의 개수, 크기 및 개체가 회수된 세대가 표시됩니다.  
  
## 일반  
  
|열|설명|  
|-------|--------|  
|**클래스 이름**|할당된 형식의 클래스 이름입니다.|  
|**프로세스 ID**|프로파일링 실행의 프로세스 ID입니다.|  
|**프로세스 이름**|프로세스의 이름입니다.|  
|**모듈 이름**|함수가 포함된 모듈의 이름입니다.|  
|**모듈 경로**|함수가 포함된 모듈의 경로입니다.|  
  
## 인스턴스 데이터  
 인스턴스 데이터는 프로파일링 실행 시 만들어진 형식 개체의 개수와 가비지 수집기에서 개체 할당을 해제한 세대를 나타냅니다.  
  
|열|설명|  
|-------|--------|  
|**인스턴스**|이 형식 개체의 할당 수입니다.|  
|**총 인스턴스 비율\(%\)**|프로파일링 실행 시 수행된 총 할당 수의 비율입니다.|  
|**수집한 Gen 0 인스턴스**|가비지 수집 알고리즘의 세대 0에서 할당이 해제된 형식 인스턴스의 개수입니다.|  
|**수집한 Gen 1 인스턴스**|가비지 수집 알고리즘의 세대 1에서 할당이 해제된 형식 인스턴스의 개수입니다.|  
|**수집한 Gen 2 인스턴스**|가비지 수집 알고리즘의 세대 2에서 할당이 해제된 형식 인스턴스의 개수입니다.|  
|**마지막에 활성 상태인 인스턴스**|프로파일링 실행이 종료될 때까지 할당이 해제되지 않은 형식 인스턴스의 개수입니다.|  
  
## 크기\(바이트\) 데이터  
 크기\(바이트\) 데이터는 프로파일링 실행 시 만들어진 형식 개체의 크기와 개체 할당이 해제된 각 세대에서 회수된 메모리 양을 나타냅니다.  
  
|열|설명|  
|-------|--------|  
|**할당된 총 바이트**|모든 형식 인스턴스의 총 바이트 수입니다.|  
|**총 바이트 비율\(%\)**|프로파일링 실행 시 할당된 총 바이트 수 중 이 형식 인스턴스에 대해 할당된 바이트 수의 비율입니다.|  
|**수집한 Gen 0 바이트**|가비지 수집 알고리즘의 세대 0에서 할당이 해제된 형식 인스턴스의 크기입니다.|  
|**수집한 Gen 1 바이트**|가비지 수집 알고리즘의 세대 1에서 할당이 해제된 형식 인스턴스의 크기입니다.|  
|**수집한 Gen 2 바이트**|가비지 수집 알고리즘의 세대 2에서 할당이 해제된 형식 인스턴스의 크기입니다.|  
  
## 대형 개체 힙 데이터  
 .NET 메모리 할당자는 관리되는 표준 힙이 아닌 별도의 위치에서 대형 개체를 관리합니다.  대형 개체 힙 데이터는 이 위치에서 관리된 형식 개체의 개수와 크기를 나타냅니다.  
  
|열|설명|  
|-------|--------|  
|**수집된 대형 개체 힙 인스턴스**|대형 개체 힙에 있었으며 프로파일링 실행 시 수집된 이 형식 인스턴스의 개수입니다.|  
|**수집된 대형 개체 힙 바이트**|대형 개체 힙에 있었으며 프로파일링 실행 시 수집된 이 형식 인스턴스의 크기\(바이트\)입니다.|  
  
## 참고 항목  
 [.NET 메모리 데이터 뷰](../profiling/dotnet-memory-data-views.md)