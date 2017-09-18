---
title: "방법: 명령 프롬프트에서 프로파일러 비교 보고서 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 00548d16-eb5b-46f7-8a65-862f98a43831
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# 방법: 명령 프롬프트에서 프로파일러 비교 보고서 만들기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

두 프로파일링 데이터 파일\(.VSP 또는 .VSPS\)의 성능 데이터를 비교하는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로파일링 도구 보고서를 생성할 수 있습니다.  이 보고서에는 프로파일링 세션 간에 나타나는 차이점, 성능 재발 및 향상 내용이 표시됩니다.  보고서의 값은 지정한 첫 번째 파일을 기준으로 한 델타 또는 변경 사항을 나타냅니다.  이 델타는 기준 값인 이전 값과 새 분석에서 얻은 결과 값 간의 차이를 확인하여 계산됩니다.  프로파일러 데이터는 코드의 함수, 응용 프로그램의 모듈, 줄, IP\(명령 포인터\) 및 형식을 기준으로 비교될 수 있습니다.  
  
 비교 범주의 식별자 목록을 표시하려면 다음 명령줄을 입력합니다.  
  
 **VSPerfReport \/querydifftables**  *VspFileName1* *VspFileName2*  
  
 비교 보고서를 만들려면 다음 구문을 사용합니다.  
  
 **VSPerfReport \/diff**  `VspFileName1` *VspFileName2* \[**\/**`Options`\]  
  
 다음 표의 옵션을 **VSPerfReport \/diff** 명령줄에 추가할 수 있습니다.  
  
|옵션|설명|  
|--------|--------|  
|**DiffThreshold:**\[*Value*\]|차이가 이 백분율 임계값보다 낮으면 차이를 무시합니다.  또한 이 임계값보다 낮은 값이 있는 새 데이터는 표시되지 않습니다.|  
|**DiffTable:** *TableName*|이 테이블을 사용하여 파일을 비교합니다.  기본적으로 함수 테이블이 사용됩니다.  **VSPerfReport \/querydifftables**에 나열된 식별자를 지정합니다.|  
|**DiffColumn:** *ColumnName*|이 열을 사용하여 값을 비교합니다.  기본적으로 전용 샘플 비율\(%\) 열이 사용됩니다.  **VSPerfReport \/querydifftables**에 나열된 식별자를 지정합니다.|