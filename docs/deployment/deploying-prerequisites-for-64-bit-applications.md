---
title: "64 비트 응용 프로그램에 대 한 필수 구성 요소 배포 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- deploying applications [Visual Studio], 64-bit
- 64-bit [Visual Studio]
- 64-bit programming [Visual Studio]
- 64-bit applications [Visual Studio]
ms.assetid: 87399e20-5510-41e4-b5b7-4a87c5773f21
caps.latest.revision: "23"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: 6e0134b0a0a6151b6ae6544f1ad8272a6d4cac47
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="deploying-prerequisites-for-64-bit-applications"></a>64비트 응용 프로그램의 필수 구성 요소 배포
ClickOnce 배포에서는 64비트 플랫폼에 응용 프로그램을 설치할 수 있습니다. 대상 플랫폼은 **x86** 32 비트 플랫폼에 대 한 **x64** AMD64 / EM64T 명령 집합을 지 원하는 컴퓨터 및 **Itanium** 64 비트 Itanium 프로세서에 대 한 합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 다음 테이블에는 64비트 응용 프로그램 설치의 필수 구성 요소로 사용할 수 있는 재배포 가능 파일이 나와 있습니다.  
  
 64비트 구성 요소가 없는 필수 구성 요소를 선택하면 선택한 패키지를 64비트 플랫폼에서 사용할 수 없다는 경고가 표시될 수 있습니다.  
  
|재배포 가능 파일|x64 지원|IA64 지원|  
|---------------------|-----------------|------------------|  
|[!INCLUDE[vsto_runtime](../deployment/includes/vsto_runtime_md.md)]|예|아니요|  
|Visual C++ 2010 런타임 라이브러리(IA64)|아니요|예|  
|Visual C++ 2010 런타임 라이브러리(x64)|예|아니요|  
|Microsoft .NET Framework 4(x86 및 x64)|예||  
|Microsoft .NET Framework 4 Client Profile(x86 및 x64)|예||  
  
## <a name="see-also"></a>참고 항목  
 [응용 프로그램, 서비스 및 구성 요소 배포](../deployment/deploying-applications-services-and-components.md)   
 [방법: ClickOnce 응용 프로그램을 사용하여 필수 조건 설치](../deployment/how-to-install-prerequisites-with-a-clickonce-application.md)   
 [64비트 응용 프로그램](http://msdn.microsoft.com/Library/fd4026bc-2c3d-4b27-86dc-ec5e96018181)