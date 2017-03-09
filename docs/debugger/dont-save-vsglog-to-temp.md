---
title: "DONT_SAVE_VSGLOG_TO_TEMP | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f27ab0e6-9575-4ca0-9901-37d3e5c3a2f5
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# DONT_SAVE_VSGLOG_TO_TEMP
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

그 존재가 그래픽 로그 파일은 사용자의 임시 파일 디렉터리에 저장할지 여부를 정의 합니다.  
  
## 구문  
  
```cpp  
#define DONT_SAVE_VSGLOG_TO_TEMP  
```  
  
## 값  
 전처리기 기호는 그 존재 여부에 의해 그래픽 로그 파일이 있는지 사용자의 임시 파일 디렉터리에 저장되는지 여부를 결정합니다.  이 기호가 정의 된 경우, `VSG_DEFAULT_RUN_FILENAME` 에 의해 정의된 파일 이름은 캡처한 응용 프로그램의 현재 디렉터리에 상대적 이거나 절대 경로입니다. 그렇지 않으면, `VSG_DEFAULT_RUN_FILENAME` 에 의해 정의된 파일 이름은 사용자의 임시 파일 디렉터리를 기준으로 한 경로이지만 절대 경로가 될 순 없습니다.  
  
## 설명  
 해당 사용자의 권한에 따라 그래픽 로그 파일은 임의 위치에 저장하지 못할 수 있습니다.  저장할 위치가 사용자에 의해 쓰일지 안쓰일지 확실하지 않은 경우, 그래픽 로그를 사용자의 임시 파일 디렉토리나 다른 좋은 위치에 저장하는것이 좋습니다.  
  
 그래픽 로그 파일을 임시 파일 디렉터리에 저장 하지 않도록 하려면 `vsgcapture.h` 을 포함하기 전에 `DONT_SAVE_VSGLOG_TO_TEMP` 을 정의합니다.  
  
## 예제  
 이 예제에서는 절대 경로를 호스트 컴퓨터에서 그래픽 로그 파일을 저장 하는 방법을 보여 줍니다.  
  
```  
// Define DONT_SAVE_VSGLOG_TO_TEMP and VSG_DEFAULT_RUN_FILENAME before including vsgcapture.h  
#define DONT_SAVE_VSGLOG_TO_TEMP  
#define VSG_DEFAULT_RUN_FILENAME L"C:\\Graphics Diagnostics Captures\\default.vsglog"  
  
#include <vsgcapture.h>  
  
```  
  
## 참고 항목  
 [VSG\_DEFAULT\_RUN\_FILENAME](../debugger/vsg-default-run-filename.md)