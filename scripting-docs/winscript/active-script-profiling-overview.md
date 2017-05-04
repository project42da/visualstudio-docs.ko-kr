---
title: "액티브 스크립트 프로파일링 개요 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "액티브 스크립트 프로파일링"
ms.assetid: eec2f413-6605-4df4-a86f-4919755e9358
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# 액티브 스크립트 프로파일링 개요
[액티브 스크립트 프로파일러 인터페이스](../winscript/reference/active-script-profiler-interfaces.md) 는 스크립트 엔진의 프로 파일링을 사용 합니다.  활성 스크립트 프로 파일링은 다음과 같은 부분으로 구성 되어 있습니다.  
  
-   언어 엔진  
  
-   호스트  
  
-   프로파일러  
  
## 언어 엔진  
 스크립트 언어 엔진을 실행합니다.  실행할 때 스크립트 코드를 프로 파일링을 사용할 수 있는 메서드를 제공 합니다.  프로 파일링이 활성화 되 면 언어 엔진 클래스 식별자 \(CLSID\)의 프로파일러 COM 개체를 인수로 사용 합니다.  프로파일러 COM 개체의 인스턴스를 만들고 다양 한 이벤트가 발생할 때 프로파일러를 호출 합니다.  
  
 구현 언어 엔진 [IActiveScriptProfilerControl 인터페이스](../winscript/reference/iactivescriptprofilercontrol-interface.md).  
  
> [!NOTE]
>  [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 언어 런타임 JS\_PROFILER 환경 변수에 프로 파일링을 사용 해야 하는지 여부를 확인 하려면 생성을 확인 합니다.  이 변수는 프로파일러의 CLSID에 설정 되어 있으면 언어 런타임 변수의 값을 사용 하 여 만들 수 있는 프로파일러를 확인 하는 프로파일러 COM 개체의 인스턴스를 만듭니다.  
  
## 호스트  
 호스트 언어 엔진을 만들고 실행 될 스크립트와 언어 엔진을 제공 합니다.  또한 스마트 호스트 디버깅 또는 프로 파일링 때 더 나은 정보를 제공 하는 디버거 나 프로파일러에서 사용할 수 있습니다 있는 문서 컨텍스트를 제공 합니다.  
  
## 프로파일러  
 다양 한 이벤트가 발생할 때 프로파일러 언어 엔진에서 호출을 받습니다.  프로파일러 COM 개체로 등록 되어 있어야 하며 구현 해야는 [IActiveScriptProfilerCallback 인터페이스](../winscript/reference/iactivescriptprofilercallback-interface.md) 인터페이스.  
  
## 참고 항목  
 [액티브 스크립트 프로파일러 인터페이스](../winscript/reference/active-script-profiler-interfaces.md)