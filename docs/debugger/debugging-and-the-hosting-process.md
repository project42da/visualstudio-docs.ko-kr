---
title: "디버깅 및 호스팅 프로세스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "디버깅[Visual Studio], 호스팅 프로세스"
  - "호스팅 프로세스"
ms.assetid: d0f0b9a6-2a6e-463d-b6ea-9518ee727933
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# 디버깅 및 호스팅 프로세스
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Visual Studio 호스팅 프로세스를 사용하면 디버거 성능을 향상시킬 수 있고 부분 신뢰 디버깅 및 디자인 타임 식 계산 등과 같은 새로운 디버거 기능을 사용할 수 있습니다. 필요한 경우 호스팅 프로세스를 비활성화할 수 있습니다. 자세한 내용은 [방법: 호스팅 프로세스 비활성화](../ide/how-to-disable-the-hosting-process.md)을 참조하세요. 다음 섹션에서는 호스팅 프로세스를 사용하는 경우와 사용하지 않는 경우의 몇 가지 디버깅 차이점에 대해 설명합니다.  
  
## 부분 신뢰 디버깅 및 ClickOnce 보안  
 부분 신뢰 디버깅에는 호스팅 프로세스가 필요합니다. 호스팅 프로세스를 비활성화하면 **프로젝트 속성**의 **보안** 페이지에서 부분 신뢰 보안을 활성화한 경우라 해도 부분 신뢰 디버깅이 실행되지 않습니다. 자세한 내용은 [방법: 호스팅 프로세스 비활성화](../ide/how-to-disable-the-hosting-process.md) 및 [방법: 부분 신뢰 응용 프로그램 디버깅](../debugger/how-to-debug-a-partial-trust-application.md)를 참조하세요.  
  
## 디자인 타임 식 계산  
 디자인 타임 식에는 항상 호스팅 프로세스가 사용됩니다.**프로젝트 속성**에서 호스팅 프로세스를 비활성화하면 클래스 라이브러리 프로젝트에 대한 디자인 타임 식 계산이 비활성화됩니다. 다른 프로젝트 형식에 대해서는 디자인 타임 식 계산이 비활성화되지 않습니다. 대신 Visual Studio가 실제 실행 파일을 시작하고 호스팅 프로세스 없이 디자인 타임 계산에 이 실행 파일을 사용합니다. 이러한 차이로 인해 서로 다른 결과가 발생할 수 있습니다.  
  
## AppDomain.CurrentDomain.FriendlyName의 반환 결과  
 `AppDomain.CurrentDomain.FriendlyName`은 호스팅 프로세스가 활성화되어 있는지 여부에 따라 서로 다른 결과를 반환합니다. 호스팅 프로세스를 사용할 수 있는 상태에서 `AppDomain.CurrentDomain.FriendlyName`을 호출하면 *app\_name*`.vhost.exe`이 반환됩니다. 호스팅 프로세스를 사용할 수 없는 상태에서 호출하면 *app\_name*`.exe`이 반환됩니다.  
  
## Assembly.GetCallingAssembly\(\).FullName의 반환 결과  
 `Assembly.GetCallingAssembly().FullName`은 호스팅 프로세스가 활성화되어 있는지 여부에 따라 서로 다른 결과를 반환합니다. 호스팅 프로세스를 사용할 수 있는 상태에서 `Assembly.GetCallingAssembly().FullName`을 호출하면 `mscorlib`가 반환됩니다. 호스팅 프로세스를 사용할 수 없는 상태에서 `Assembly.GetCallingAssembly().FullName`을 호출하면 응용 프로그램 이름이 반환됩니다.  
  
## 참고 항목  
 [호스팅 프로세스\(vshost.exe\)](../ide/hosting-process-vshost-exe.md)   
 [방법: 부분 신뢰 응용 프로그램 디버깅](../debugger/how-to-debug-a-partial-trust-application.md)   
 [방법: 호스팅 프로세스 비활성화](../ide/how-to-disable-the-hosting-process.md)