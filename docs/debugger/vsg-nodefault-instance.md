---
title: "VSG_NODEFAULT_INSTANCE | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 19c95b0d-9a4d-441f-9ed7-3acb39e67521
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# VSG_NODEFAULT_INSTANCE
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

프로그래밍 캡처 인터페이스를 제공하는 [VsgDbg 클래스](../debugger/vsgdbg-class.md) 클래스의 기본 정의가 존재하느냐에 의해 정의됩니다.  
  
## 구문  
  
```cpp  
#define VSG_NODEFAULT_INSTANCE  
```  
  
## 값  
 전처리기 기호는 그 존재가 있고 없고에 따라서 해당 `VsgDbg` 클래스의 기본 인스턴스가 있는지 여부를 결정합니다.  이 기호가 정의된 경우, `VsgDbg` 클래스의 기본 인스턴스는 제공되지 않습니다. 그렇지 않으면 기본 인스턴스는 제공되고 프로그램을 실행 하기 전에 초기화 됩니다.  
  
 캡처 프로그램 인터페이스는 포인터를 통해 전역 범위, `g_pVsgDbg`에 있는 경우 제공됩니다.  
  
```  
VsgDbg *g_pVsgDbg;  
```  
  
## 설명  
 기본 인스턴스는 대개 충분 하지만 DLL 외부에서 D3D 장지가 만들어 졌을 때 DLL 내부에서 프로그래밍 캡처 인터페이스 사용하기 위해서는 `VsgDbg` 클래스의 인스턴스를 직접 만들고 관리해야 합니다.  이 방법으로 프로그래밍 캡처 API의 사용자 인터페이스를 관리 하는 경우, 오버 헤드를 피하기 위해 `VSG_NODEFAULT_INSTANCE` 를 정의하여 기본 인스턴스를 비활성화 합니다.  
  
 기본 인스턴스가 비활성화된 경우, 이것은 프로그램이 실행되기 전에 자동으로 초기화되고 프로그램이 종료되면 자동으로 소멸 됩니다.  이 인스턴스를 명시적으로 초기화 또는 초기화를 취소할 필요가 없습니다.  
  
 기본 인스턴스를 사용하지 않으려면, 프로그램에서 `vsgcapture.h` 을 포함하기 전에 `VSG_NODEFAULT_INSTANCE` 을 정의해야 합니다.  
  
## 예제  
 이 예제에서는 기본 인스턴스를 사용 하지 않도록 설정 하는 방법을 보여 줍니다.  
  
```  
// Define VSG_NODEFAULT_INSTANCE before including vsgcapture.h  
#define VSG_NODEFAULT_INSTANCE  
  
#include <vsgcapture.h>  
```