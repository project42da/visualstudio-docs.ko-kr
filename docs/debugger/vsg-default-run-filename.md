---
title: "VSG_DEFAULT_RUN_FILENAME | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ea549d2f-c857-458c-93c7-bc5a2d11d15d
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# VSG_DEFAULT_RUN_FILENAME
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

그래픽 로그 파일의 기본 파일 이름을 정의합니다.  
  
## 구문  
  
```cpp  
#define VSG_DEFAULT_FILENAME filename  
```  
  
#### 매개 변수  
 `filename`  
 그래픽 정보를 프로그래밍 방식으로 캡처한 그래픽 로그 파일에 기본적으로 지정된 파일 이름입니다.  
  
## 값  
 그래픽 로그 파일의 파일 이름을 나타내는 문자열 리터럴입니다.  기본적으로 L"default.vsglog" 입니다.  
  
```cpp  
#define VSG_DEFAULT_FILENAME L"default.vsglog"  
```  
  
## 설명  
 전처리기 기호 `DONT_SAVE_VSGLOG_TO_TEMP` 가 정의된 경우, 파일 이름은 캡처된 응용 프로그램의 현재 디럭테리의 상대 또는 절대 경로입니다. 그렇지 않으면 사용자의 임시 파일 디렉터리를 기준으로 한 경로이며 이 경로는 절대 경로가 될 수 없습니다.  
  
 정의된 파일 이름을 변경 하려면 프로그램에 `vsgcapture.h` 를 포함하기 전에 재정의 해야 합니다.  
  
## 예제  
 이 예제에서는 캡처 파일의 기본 파일 이름을 변경 하는 방법을 보여 줍니다.  
  
```cpp  
// Redefine the default capture filename before including vsgcapture.h  
#define VSG_DEFAULT_FILENAME L"capture.vsglog"  
  
#include <vsgcapture.h>  
```  
  
## 참고 항목  
 [DONT\_SAVE\_VSGLOG\_TO\_TEMP](../debugger/dont-save-vsglog-to-temp.md)