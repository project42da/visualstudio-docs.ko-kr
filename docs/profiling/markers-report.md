---
title: "표식 보고서 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.cv.threads.report.markers"
ms.assetid: 829ce099-172e-4c7e-bbd0-578b110c59bd
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 표식 보고서
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

마커 보고서 표시 된 시간 내에 마커를 나열합니다.  패닝 또는 확대\/축소, 레인, 숨기기 마커 나타나거나 사라지게 될 수 있습니다.  보고서는 각 표식에 대해 다음이 정보가 포함 되어 있습니다.  
  
-   때 시작, 추적의 시작 부분을 기준으로 하는 시간입니다.  
  
-   지속 시간이 길어집니다.  인스턴트를 나타내므로 기간은 0 플래그 메시지가 됩니다.  
  
-   스레드의 ID를 생성한 ID  
  
-   이벤트 추적에 대 한 Windows \(ETW\) 공급자 생성 된 것입니다.  
  
-   작성 된 마커 시리즈입니다.  
  
-   이벤트가 속한 범주입니다.  
  
-   중요도입니다.  
  
-   \(범위, 플래그, 메시지\)의 형식입니다.  
  
-   나타내는 것을 자세히 설명  
  
 **내보내기** 마커 보고서를 CSV 파일로 저장 하는 단추를 선택합니다.  다른 응용 프로그램 또는 도구를 사용 하 여 CSV 파일에 데이터를 사용할 수 있습니다.  
  
> [!NOTE]
>  마커 보고서 1000 마커를 표시할 수 있습니다.  모든 마커를 전체 보고서를 CSV 파일로 내보냅니다.