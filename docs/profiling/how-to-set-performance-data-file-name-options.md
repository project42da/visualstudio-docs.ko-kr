---
title: "방법: 프로파일링 데이터 파일 이름 옵션 설정 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d7a8d6b9-ab23-46fb-98ed-774781157860
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# 방법: 프로파일링 데이터 파일 이름 옵션 설정
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

기본적으로 프로파일링 데이터 파일\(.vsp\)은 다음 구문을 사용하여 저장합니다.  
  
 *Path\\VSP\-File\\YYMMDD\(N\)* **.vsp**  
  
 성능 세션에 대한 속성 대화 상자의 일반 페이지에서 명명 매개 변수를 변경할 수 있습니다.  
  
 **요구 사항**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
|||  
|-|-|  
|*Path*|보고서를 포함하는 디렉터리입니다.  기본 위치는 솔루션 폴더나 사용자의 프로젝트 및 솔루션에 사용하는 기본 위치입니다.|  
|*VSP\-File*|프로파일링 데이터 파일의 이름입니다.  기본 이름은 프로파일링된 솔루션 또는 실행 파일의 이름입니다.|  
|*YYMMDD*|프로파일링 데이터가 수집된 년, 월, 일을 나타내는 날짜 스탬프입니다.|  
|*\(N\)*|프로파일링 데이터 파일이 둘 이상이면 파일 이름에 괄호로 묶인 증분 번호가 추가됩니다.|  
  
### 성능 세션의 프로파일링 데이터 파일에 대한 명명 구문을 변경하려면  
  
1.  **성능 탐색기**에서 성능 세션의 이름을 마우스 오른쪽 단추로 클릭한 다음 **속성**을 클릭합니다.  
  
2.  **일반**을 클릭합니다.  
  
3.  **보고서**에서 다음 중 원하는 설정을 변경합니다.  
  
    |||  
    |-|-|  
    |**보고서 위치**|프로파일링 데이터 파일을 저장할 디렉터리를 지정합니다.|  
    |**보고서 이름**|파일의 기본 이름을 지정합니다.|  
    |**자동으로 세션에 새 보고서 추가**|성능 세션에 데이터 파일을 자동으로 추가하려면 이 확인란을 선택합니다.|  
    |**생성된 보고서에 증분 번호 추가**|같은 이름의 파일이 둘 이상 있을 때 파일 이름에 증분 번호를 추가하려면 이 확인란을 선택합니다.  기존 파일을 덮어쓰려면 이 확인란의 선택을 취소합니다.|  
    |**숫자에 타임스탬프 사용**|파일 이름에 날짜 스탬프를 추가하려면 이 확인란을 선택합니다.|