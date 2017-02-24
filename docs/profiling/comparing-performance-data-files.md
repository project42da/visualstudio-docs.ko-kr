---
title: "성능 데이터 파일 비교 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- profiling tools, comparing profiling tools report files
- profiling tools reports, comparing
ms.assetid: e6fda144-f21d-4912-9d16-1b8d3555a210
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: 5db97d19b1b823388a465bba15d057b30ff0b3ce
ms.openlocfilehash: 9a0b4dcb86aa4241d223dd4a1172267dd8ec20da

---
# <a name="comparing-performance-data-files"></a>성능 데이터 파일 비교
프로파일링 도구 데이터 파일 비교 기능을 통해 두 개의 보고서 파일(.VSP/또는 VSP)을 선택하고 프로파일링 세션 간에 발생하는 차이, 성능 저하 및 향상된 기능을 보여 주는 보고서를 생성할 수 있습니다.  
  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로파일링 도구의 데이터 파일 비교 보고서는 한 프로파일링 데이터 파일의 분석 결과와 다른 데이터 파일의 기본 분석 결과를 비교합니다. 두 데이터 파일은 모두 동일한 프로파일링 방법을 사용하여 생성된 것이어야 합니다. 분석된 비교 보고서는.vsps 파일로 저장됩니다.  
  
 비교 보고서 뷰는 변경된 데이터의 테이블 뷰를 표시합니다. 테이블은 델타 또는 기준선으로부터 변경을 표시합니다. 델타는 이전 값, 기준 값, 새 분석의 결과 값 간의 차이를 확인하여 계산됩니다.  
  
 프로파일러 데이터의 비교는 코드의 함수, 응용 프로그램의 모듈, 줄, IP(명령 포인터) 및 형식에 따라 달라질 수 있습니다.  
  
 비교에 사용할 수 있는 프로파일링 데이터에는 열에 표시되는 정보가 포함됩니다. 이러한 열 이름에 대한 정의는 [성능 보고서 뷰](../profiling/performance-report-views.md)를 참조하세요.  
  
 노이즈를 줄이고, 지정된 크기만큼 변경되지 않은 행의 비교 테이블 뷰에서 임의의 데이터를 필터링하도록 임계값을 설정할 수 있습니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [방법: 성능 데이터 파일 비교](../profiling/how-to-compare-performance-data-files.md)


<!--HONumber=Feb17_HO4-->


