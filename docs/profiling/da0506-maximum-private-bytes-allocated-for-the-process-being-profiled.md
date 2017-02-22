---
title: "DA0506: 프로파일링 중인 프로세스에 할당되는 최대 전용 바이트 | Microsoft Docs"
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
  - "vs.performance.rules.DA0506"
  - "vs.performance.DA0506"
  - "vs.performance.506"
ms.assetid: e9c43554-9a85-4d98-9fa4-3b19986e7b62
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# DA0506: 프로파일링 중인 프로세스에 할당되는 최대 전용 바이트
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|규칙 ID|DA0506|  
|범주|리소스 모니터링|  
|프로파일링 방법|모두|  
|메시지|이 정보는 참고용으로만 수집됩니다.  Process Private Bytes 카운터는 프로파일링하고 있는 프로세스에서 할당되어 다른 프로세스와 공유할 수 없는 가상 메모리를 측정합니다.  보고된 값은 모든 측정 간격에 걸쳐 관측된 최대값입니다.|  
|규칙 유형|정보|  
  
 샘플링, .NET 메모리 또는 리소스 경합 방법을 사용하여 프로파일링하는 경우에는 적어도 10개의 샘플을 수집하여 이 규칙을 트리거해야 합니다.  
  
## 규칙 설명  
 이 메시지는 프로세스에서 현재 할당한 가상 메모리\(전용 바이트\)의 최대 바이트 크기를 보고합니다.  전용 바이트는 프로세스에 의해 할당되어 프로세스 내에서 실행 중인 스레드에 의해서만 액세스될 수 있는 가상 메모리 위치를 나타냅니다.  
  
 32비트 컴퓨터에서 실행되는 32비트 프로세스의 경우 프로세스 주소 공간의 전용 부분에 대한 상한은 2GB입니다.  [\/3 GB](http://go.microsoft.com/fwlink/?LinkId=177831) Boot.ini 스위치를 사용하여 32 비트 프로세스는 최대 3GB의 가상 메모리를 얻을 수 있습니다.  64비트 컴퓨터에서 실행되는 32비트 프로세스는 최대 4GB의 전용 가상 메모리를 사용할 수 있습니다.  
  
 64비트 컴퓨터에서 실행되는 64비트 프로세스는 최대 8TB의 전용 가상 메모리를 사용할 수 있습니다.  
  
 보고되는 값은 프로파일링되는 프로세스가 활성 상태였던 전체 측정 간격의 최대값입니다.  
  
 프로세스 주소 공간에 대한 자세한 내용은 Windows Memory Management 설명서의 [Virtual Address Space](http://go.microsoft.com/fwlink/?LinkId=177832) 를 참조하십시오.  
  
## 규칙 데이터 사용 방법  
 보고된 값을 사용하여 프로그램의 여러 버전 또는 빌드 간에 성능을 비교하거나, 여러 프로파일링 시나리오에서의 응용 프로그램 성능을 확인할 수 있습니다.  
  
 프로세스 전용 바이트의 최대값이 프로세스 주소 공간의 가능한 최대 크기에 대한 아키텍처 제한에 근접하면 메모리 부족 예외가 발생할 수 있습니다.  자세한 내용은 MSDN Magazine에서 [메모리 문제 조사](http://go.microsoft.com/fwlink/?LinkID=177833) 를 참조하십시오.