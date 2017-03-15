---
title: "방법: 시작할 이진 파일 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.performance.property.itemlaunch"
helpviewer_keywords: 
  - "프로파일링 도구, 시작"
  - "성능 도구, 시작"
  - "성능 세션, 시작"
ms.assetid: ba77fcf4-8d78-49f1-b8f3-7dd0acf84306
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# 방법: 시작할 이진 파일 지정
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

DLL 같은 이진 파일을 프로파일링하려면 **\<Target\> 속성 페이지** 페이지 대화 상자에 정보를 입력해야 합니다.  이 정보는 DLL 프로젝트에서 호출 응용 프로그램을 찾을 수 있는 위치를 나타냅니다.  
  
 **요구 사항**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
### 시작할 실행 파일을 지정하려면  
  
1.  **성능 탐색기**에서 대상 이진 파일을 마우스 오른쪽 단추로 클릭한 다음 **속성**을 클릭합니다.  
  
2.  **속성 페이지** 대화 상자에서 **시작** 속성을 클릭합니다.  
  
3.  **프로젝트 설정 재정의** 확인란을 선택합니다.  
  
4.  **시작할 실행 파일** 텍스트 상자에서 파일 위치를 지정합니다.  
  
5.  **인수** 텍스트 상자에서 응용 프로그램을 시작하는 데 필요한 인수를 지정합니다.  
  
6.  **작업 디렉터리** 텍스트 상자에서 디렉터리 위치를 지정합니다.  
  
7.  **확인**을 클릭합니다.  
  
## 참고 항목  
 [성능 세션 구성](../profiling/configuring-performance-sessions.md)