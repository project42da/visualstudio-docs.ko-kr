---
title: "호스팅 프로세스(vshost.exe) | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- vshost.exe
- hosting process
ms.assetid: c6b9e2be-f18d-4d75-ac52-56d55784734b
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 716d19362495fccf475a068a28a9fe2acbe27b53
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="hosting-process-vshostexe"></a>호스팅 프로세스(vshost.exe)
호스팅 프로세스는 디버깅 성능을 향상하고, 부분 신뢰 디버깅을 가능하게 하고, 디자인 타임 식 계산을 가능하게 하는 Visual Studio의 기능입니다. 호스팅 프로세스 파일의 파일 이름에는 vshost가 포함되고 이 파일은 프로젝트의 출력 폴더에 저장됩니다. 자세한 내용은 [디버깅 및 호스팅 프로세스](../debugger/debugging-and-the-hosting-process.md)를 참조하세요.  
  
> [!NOTE]
>  호스팅 프로세스 파일(.vshost.exe)은 Visual Studio를 통해 사용할 수 있고 응용 프로그램에서 직접 실행되거나 배포되면 안 됩니다.  
  
## <a name="improved-debugging-performance"></a>향상된 디버깅 성능  
 호스팅 프로세스는 응용 프로그램 도메인을 만들고 디버거를 응용 프로그램과 연결합니다. 이러한 작업을 수행하면 디버깅 시작 시간과 응용 프로그램 실행 시작 시간 사이에 눈에 띄는 지연이 발생할 수 있습니다. 호스팅 프로세스를 통해 응용 프로그램 도메인을 만들고 백그라운드에서 디버거를 연결하고 응용 프로그램 실행 사이에 응용 프로그램 도메인 및 디버거 상태를 저장하는 방식으로 성능을 향상할 수 있습니다. 응용 프로그램 도메인에 대한 자세한 내용은 [응용 프로그램 도메인](/dotnet/framework/app-domains/application-domains)을 참조하세요.  
  
## <a name="partial-trust-debugging"></a>부분 신뢰 디버깅  
 **프로젝트 디자이너**의 [보안 페이지](../ide/reference/security-page-project-designer.md)에서 응용 프로그램을 부분 신뢰 응용 프로그램으로 지정할 수 있습니다. 부분 신뢰 응용 프로그램을 디버깅하려면 응용 프로그램에 대한 특별한 초기화가 필요합니다. 이 초기화는 호스팅 프로세스에서 처리됩니다.  
  
## <a name="design-time-expression-evaluation"></a>디자인 타임 식 계산  
 디자인 타임 식 계산을 사용하면 응용 프로그램을 실행할 필요 없이 **직접 실행** 창에서 코드를 테스트할 수 있습니다. 호스팅 프로세스는 디자인 타임 식 계산 중에 이 코드를 실행합니다. 자세한 내용은 [직접 실행 창](../ide/reference/immediate-window.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 및 호스팅 프로세스](../debugger/debugging-and-the-hosting-process.md)   
 [방법: 호스팅 프로세스 비활성화](../ide/how-to-disable-the-hosting-process.md)   
 [직접 실행 창](../ide/reference/immediate-window.md)   
 [응용 프로그램 도메인](/dotnet/framework/app-domains/application-domains)