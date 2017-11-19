---
title: "기록 디버깅 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7cc5ddf2-2f7c-4f83-b7ca-58e92e9bfdd2
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6507ce8544c2dc3bc9085cbcab70a87f04176c17
ms.sourcegitcommit: fb751e41929f031d1a9247bc7c8727312539ad35
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2017
---
# <a name="historical-debugging"></a>기록 디버깅
기록 디버깅은 IntelliTrace에서 수집된 정보에 의존하는 디버깅 모드입니다. 이 디버깅을 사용하면 응용 프로그램 실행 도중 앞이나 뒤로 이동하며 상태를 검사할 수 있습니다.  
  
 Visual Studio Enterprise Edition(Professional 또는 Community Edition 아님)에서 IntelliTrace를 사용할 수 있습니다.  
  
## <a name="why-use-historical-debugging"></a>기록 디버깅 사용 이유?  
 버그를 찾는 중단점을 설정하는 것은 적중하느냐 누락하느냐의 문제입니다. 코드에서 버그가 있을 것으로 의심되는 위치 가까이에 중단점을 설정하면 디버거에서 응용 프로그램을 실행할 때 중단점이 적중될 것으로 기대할 수 있고, 이에 따라 실행이 중단된 위치가 버그 소스를 노출할 수 있습니다. 그렇지 않은 경우 다른 위치에 코드에서 중단점을 설정 해 보고 하 고 문제를 찾을 때까지 테스트 단계를 반복 실행 하 고 디버거를 다시 실행 해야 합니다.  
  
 ![중단점 설정](../debugger/media/breakpointprocesa.png "BreakpointProcesa")  
  
 IntelliTrace와 기록 디버깅을 사용 하 여 응용 프로그램에서 로밍 하 고 중단점을 설정, 디버깅을 다시 시작 하지 않고 상태 (호출 스택 및 지역 변수)을 검사 하려면 수 있으며 테스트 단계를 반복할 수 있습니다. 이렇게 하면 특히 버그가 테스트 시나리오의 깊은 수준에 있어서 실행하는 데 오래 걸리는 경우 많은 시간을 절약할 수 있습니다.  
  
## <a name="how-do-i-start-using-historical-debugging"></a>기록 디버깅을 사용 하 여 시작 하려면 어떻게 해야 합니까?  
 IntelliTrace는 기본적으로 설정되어 있습니다. 사용자에 게는 관심 있는 이벤트 및 함수 호출 여부 및 전체 응용 프로그램 상태에 대 한 스냅숏을 볼 수를 결정 해야 할 됩니다. 검색할 대상 정의 대 한 자세한 내용은 참조 [IntelliTrace 기능](../debugger/intellitrace-features.md)합니다.  

 - 기록 디버깅으로 스냅숏을 참조 하십시오 [IntelliTrace 단계 백을 사용 하 여 스냅숏 보기](../debugger/how-to-use-intellitrace-step-back.md)
 - 참조 변수를 검사 하 고 코드를 탐색 하는 방법에 자세한 [기록 디버깅을 사용 하 여 앱을 검사 합니다.](../debugger/historical-debugging-inspect-app.md)
 - IntelliTrace 이벤트로 디버깅 하는 방법에 대 한 자세한 참조 [연습: IntelliTrace를 사용 하 여](../debugger/walkthrough-using-intellitrace.md)합니다.