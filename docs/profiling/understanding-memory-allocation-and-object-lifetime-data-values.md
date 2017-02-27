---
title: "프로파일링 도구에서 메모리 할당 및 개체 수명 데이터 값 이해 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - ".NET 메모리 프로파일링 방법"
  - "프로파일링 도구, .NET 메모리 방법"
ms.assetid: a22445b3-39a6-4919-8506-2b5b0ceaf77e
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# 프로파일링 도구에서 메모리 할당 및 개체 수명 데이터 값 이해
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

*.NET memory allocation* [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로파일러에서는 할당에서 만들어지거나 가비지 수집에서 제거된 개체의 크기 및 개수에 대한 정보와 해당 이벤트가 발생했을 때의 함수 *call stack*에 대한 추가 정보를 수집합니다.  *호출 스택*은 프로세서에서 실행 중인 함수에 대한 정보를 저장하는 동적 구조입니다.  
  
 **요구 사항**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
 메모리 프로파일러에서는 프로파일링되는 응용 프로그램에서 .NET Framework 개체가 할당될 때마다 컴퓨터 프로세서가 중단됩니다.  개체 수명 데이터도 수집되는 경우 프로파일러에서는 .NET Framework 가비지 수집이 수행된 후마다 프로세서를 중단합니다.  데이터는 프로파일링되는 각 함수와 각 개체 형식에 대해 집계됩니다.  
  
## 할당 데이터  
 메모리 이벤트가 발생하면 할당되거나 제거된 메모리 개체의 총 개수 및 크기가 증가합니다.  
  
 메모리 할당 이벤트가 발생하면 프로파일러에서는 호출 스택에 있는 각 함수에 대해 샘플 개수를 증가시킵니다.  데이터가 수집될 때는 호출 스택에 있는 하나의 함수에서만 현재 해당 함수 본문의 코드를 실행하고 있는 것입니다.  스택의 다른 함수는 함수 호출의 계층 구조에서 해당 함수가 호출한 함수가 반환되기를 기다리고 있는 부모 함수입니다.  
  
-   할당 이벤트의 경우, 프로파일러에서는 현재 명령을 실행 중인 함수의 *전용* 샘플 수를 증가시킵니다.  전용 샘플은 해당 함수의 총\(*포괄*\) 샘플 수에도 포함되므로 현재 활성 상태인 함수의 포괄 샘플 수도 증가합니다.  
  
-   프로파일러에서는 호출 스택에 있는 다른 모든 함수의 포괄 샘플 수를 증가시킵니다.  
  
## 수명 데이터  
 .NET Framework 가비지 수집기는 응용 프로그램의 메모리 할당 및 해제를 관리합니다.  가비지 수집기의 성능을 최적화하기 위해 관리되는 힙은 0세대, 1세대 및 2세대의 3개 세대로 나뉩니다.  런타임 가비지 수집기는 새 개체를 0세대에 저장합니다.  수집 후에도 남아 있는 개체는 수준이 올라가 1세대와 2세대에 저장됩니다.  
  
 가비지 수집기는 전체 개체 세대의 할당을 해제하여 메모리를 회수합니다.  프로파일링된 응용 프로그램에서 만든 개체의 경우 개체 수명 뷰에 해당 개체의 개수, 크기 및 개체가 회수된 세대가 표시됩니다.