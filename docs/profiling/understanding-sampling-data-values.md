---
title: "프로파일링 도구에서 샘플링 데이터 값 이해 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "샘플링 프로파일링 방법"
  - "프로파일링 도구, 샘플링"
ms.assetid: fad540a8-24b6-4ff9-91ce-e67e9a58399d
caps.latest.revision: 22
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 22
---
# 프로파일링 도구에서 샘플링 데이터 값 이해
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로파일링 도구의 *샘플링* 프로파일링 방법은 컴퓨터 프로세서를 설정된 간격으로 중단하고 함수 호출 스택을 수집합니다.  *호출 스택*은 프로세서에서 실행 중인 함수에 대한 정보를 저장하는 동적 구조입니다.  
  
 **요구 사항**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
 프로파일러 분석을 수행하면 프로세서가 대상 프로세스에서 코드를 실행 중인지 여부를 알 수 있습니다.  프로세서가 대상 프로세스에서 코드를 실행하고 있지 않은 경우 샘플이 삭제됩니다.  
  
 프로세서가 대상 코드를 실행 중인 경우 프로파일러는 호출 스택의 각 함수에 대해 샘플 수를 증가시킵니다.  샘플을 가져올 때 호출 스택에 있는 하나의 함수에서만 현재 코드를 실행하고 있습니다.  스택의 다른 함수는 함수 호출의 계층 구조에서 자식이 반환되기를 기다리고 있는 부모 함수입니다.  
  
 샘플 이벤트의 경우, 프로파일러에서는 현재 명령을 실행 중인 함수의 *전용* 샘플 수를 증가시킵니다.  전용 샘플은 해당 함수의 총\(*포괄*\) 샘플 수에도 포함되므로 현재 활성 상태인 함수의 포괄 샘플 수도 증가합니다.  
  
 프로파일러에서는 호출 스택에 있는 다른 모든 함수의 포괄 샘플 수를 증가시킵니다.  
  
## 포괄 샘플  
 대상 함수 실행 시 수집되는 총 샘플 수입니다.  
  
 여기에는 함수 코드를 직접 실행할 때 수집된 샘플과 대상 함수에 의해 호출된 자식 함수를 실행할 때 수집된 샘플이 포함됩니다.  
  
## 전용 샘플  
 대상 함수의 명령을 직접 실행할 때 수집되는 샘플 수입니다.  
  
 전용 샘플에는 대상 함수에 의해 호출된 함수를 실행할 때 수집되는 샘플은 포함되지 않습니다.  
  
## 포괄 백분율  
 프로파일링 실행 시 함수 또는 데이터 범위의 포괄 샘플에 해당하는 총 포괄 샘플 수의 백분율  
  
## 전용 백분율  
 프로파일링 실행 시 함수 또는 데이터 범위의 전용 샘플에 해당하는 총 전용 샘플 수의 백분율  
  
## 참고 항목  
 [방법: 수집 방법 선택](../profiling/how-to-choose-collection-methods.md)   
 [프로파일링 도구 데이터 분석](../profiling/analyzing-performance-tools-data.md)