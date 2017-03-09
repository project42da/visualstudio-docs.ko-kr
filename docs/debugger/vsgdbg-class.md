---
title: "VsgDbg 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6722263c-ccef-40c7-a0ae-87a863fbab00
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# VsgDbg 클래스
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

그래픽 진단 응용 프로그램의 구성 요소의 프로그래밍 컨트롤에 대한 인터페이스를 나타냅니다.  
  
## 구문  
  
```cpp  
class VsgDbg;  
```  
  
## 멤버  
 `VsgDbg` 클래스에는 다음과 같은 멤버를 지원합니다.  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[VsgDbg::VsgDbg\(생성자\)](../debugger/vsgdbg-vsgdbg-constructor.md)|`VsgDbg` 클래스의 인스턴스를 생성하고, 필요에 따라 적극적으로 캡처 및 그래픽 정보를 기록하려면 그래픽 진단 응용 프로그램에서 구성 요소를 준비합니다.|  
|[VsgDbg::~VsgDbg\(소멸자\)](../debugger/vsgdbg-tilde-vsgdbg-destructor.md)|`VsgDbg` 클래스의 인스턴스를 제거합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[AddMessage](../debugger/addmessage.md)|그래픽 진단 HUD \(Head\-Up Display\) 에 사용자 지정 메시지를 추가합니다.|  
|[BeginCapture](../debugger/begincapture.md)|`EndCapture` 로 끝나는 캡처 간격이 시작됩니다.|  
|[CaptureCurrentFrame](../debugger/capturecurrentframe.md)|그래픽 로그 파일에 현재 프레임의 나머지 부분을 캡처합니다.|  
|[복사\(프로그램 방식 캡처\)](../debugger/copy-programmatic-capture.md)|액티브 그래픽 \(.vsglog\) 로그 파일의 내용을 새 파일에 복사합니다.|  
|[EndCapture](../debugger/endcapture.md)|`BeginCapture` 시작된 캡처 간격을 종료합니다.|  
|[Init](../debugger/init.md)|그래픽 진단 응용 프로그램의 구성 요소를 준비하여 그래픽 정보를 적극적으로 캡처 및 기록합니다.|  
|[ToggleHUD](../debugger/togglehud.md)|그래픽 진단 HUD 오버레이를 켜거나 끕니다.|  
|[UnInit](../debugger/uninit.md)|그래픽 로그 파일을 종료하고 응용 프로그램이 그래픽 정보를 기록하는 동안 사용된 리소스를 해제 합니다.|  
  
## 설명  
 `VsgDbg` 클래스는 그래픽 진단 기능을 프로그래밍 방식으로 제어하는데 사용할 수 있는 인터페이스를 나타냅니다.  그래픽 정보를 캡처 기록 하지 않은 중에도 일부 기능을 사용할 수 있습니다. 여기서의 기능은 `AddMessage` 멤버 함수 와 `ToggleHUD` 멤버 함수를 포함합니다.  다른 멤버 함수들은 그래픽 진단 유틸리티를 시작 하거나 중지할 그래픽 진단 응용 프로그램의 구성 요소를 준비 하거나, 적극적으로 그래픽 정보를 로그 파일에 기록 및 캡처 하는 동안 호출되야 합니다.