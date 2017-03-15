---
title: "VsgDbg::VsgDbg(생성자) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 670651e6-5e79-4845-b0c2-671beb7055a8
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# VsgDbg::VsgDbg(생성자)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Boolean 매개 변수를 기반으로 그래픽 정보를 기록 및 캡처 하는 그래픽 진단 프로그램의 응용 프로그램 구성 요소 유무에 관계 없이 `VsgDbg` 클래스의 인스턴스를 생성합니다.  
  
## 구문  
  
```cpp  
VsgDbg(  
  bDefaultInit  
);  
```  
  
#### 매개 변수  
 `bDefaultInit`  
 그래픽 정보를 적극적으로 캡처 및 기록할 수 있도록 그래픽 진단 응용 프로그램에서 구성 요소를 준비하도록 지정 하려면 `true`를, 그렇지 않으면 `false` 를 사용합니다.  
  
## 설명  
 `true` 로 설정된 `bDefaultInit` 을 사용하여 생성자를 호출하는 경우, 그래픽 로그 파일의 파일 이름은 응용 프로그램에 `vsgcapture.h` 가 포함되기 전에 `DONT_SAVE_VSGLOG_TO_TEMP` 및 `VSG_DEFAULT_RUN_FILENAME` 전처리기 기호가 정의되는 방식에 의해 결정됩니다.  
  
 `false` 로 설정된 `bDefaultInit` 을 사용하여 생성자를 호출 하는 경우, 구성 요소를 적극적으로 캡처하고 `Init` 함수를 호출하여 나중에 그래픽 정보를 기록하도록 그래픽 진단 응용 프로그램을 준비할 수 있습니다.  
  
## 참고 항목  
 [VsgDbg::~VsgDbg\(소멸자\)](../debugger/vsgdbg-tilde-vsgdbg-destructor.md)   
 [Init](../debugger/init.md)   
 [DONT\_SAVE\_VSGLOG\_TO\_TEMP](../debugger/dont-save-vsglog-to-temp.md)   
 [VSG\_DEFAULT\_RUN\_FILENAME](../debugger/vsg-default-run-filename.md)