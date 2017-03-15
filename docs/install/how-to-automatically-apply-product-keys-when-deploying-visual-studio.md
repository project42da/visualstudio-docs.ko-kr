---
title: "방법: Visual Studio를 배포할 때 제품 키를 자동으로 적용 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-install"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d79260be-6234-4fd3-89b5-a9756b4a93c1
caps.latest.revision: 10
caps.handback.revision: 5
author: "TerryGLee"
ms.author: "tglee"
manager: "ghogen"
---
# 방법: Visual Studio를 배포할 때 제품 키를 자동으로 적용
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Visual Studio의 배포를 자동화하는 데 사용되는 스크립트의 일부로 제품 키를 프로그래밍 방식으로 적용할 수 있습니다. 제품 키는 Visual Studio의 설치 중이나 설치가 완료된 후에 프로그래밍 방식으로 장치에서 설정할 수 있습니다.  
  
## 설치 중 라이선스 적용  
 \/ProductKey 매개 변수를 사용하여 Visual Studio의 설치 프로세스 중에 제품 키를 적용할 수 있습니다. 이 설치 매개 변수를 \/Silent 매개 변수와 함께 사용하여 최종 사용자에게 이미 사용이 허가된 상태로 Visual Studio를 설치할 수 있습니다. \/ProductKey 매개 변수를 사용하려면 명령 프롬프트를 엽니다. 설치 프로그램\(예: vs\_enterprise.exe 또는 vs\_professional.exe\)를 실행하고 대시가 포함되지 않은 제품 키\(25자\)를 사용하여 \/ProductKey 매개 변수를 설정합니다.  
  
 다음은 AAAAABBBBBCCCCCDDDDDEEEEEEE 제품 키를 사용하여 Visual Studio 2015 Enterprise를 설치하는 예제 명령입니다.  
  
 `vs_enterprise.exe [any other setup parameters] /ProductKey AAAAABBBBBCCCCCDDDDDDEEEEEE`  
  
## 설치 후 라이선스 적용  
 대상 컴퓨터에서 자동 모드로 StorePID.exe 유틸리티를 사용하여 설치된 Visual Studio 버전을 제품 키로 활성화할 수 있습니다. StorePID.exe는 Visual Studio와 함께 **\<drive\>:\\\\Program Files \(x86\)\\Microsoft Visual Studio 14.0\\Common7\\IDE\\StorePID.exe**에 설치되는 유틸리티 프로그램입니다.  
  
 System Center 에이전트나 관리자 권한 명령 프롬프트를 사용하여 높은 권한으로 StorePID.exe를 실행합니다. 이때 StorePID.exe 뒤에 제품 키\(대시 포함\)와 MPC\(Microsoft Product Code\)를 붙입니다. 제품 키에 대시를 포함해야 합니다.  
  
 `StorePID.exe [product key including the dashes] [MPC]`  
  
 다음은 "AAAAA\-BBBBB\-CCCCC\-DDDDDD\-EEEEEE" 제품 키를 사용하여 MPC가 07060인 Visual Studio 2015 Enterprise를 설치하는 예제 명령줄입니다.  
  
 `C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\IDE\StorePID.exe AAAAA-BBBBB-CCCCC-DDDDDD-EEEEEE 07060`  
  
 다음 표에는 Visual Studio의 각 버전에 대한 MPC 코드가 나와 있습니다.  
  
|Visual Studio 버전|MPC|  
|----------------------|---------|  
|Visual Studio Enterprise 2015|07060|  
|Visual Studio Professional 2015|07062|  
|Visual Studio Ultimate 2013|06181|  
|Visual Studio Premium 2013|06191|  
|Visual Studio Professional 2013|06177|  
  
 제품 키를 가져오는 방법에 대한 자세한 내용은 [방법: Visual Studio 제품 키 찾기](../install/how-to-locate-the-visual-studio-product-key.md)를 참조하세요.  
  
 StorePID.exe는 제품 키를 성공적으로 적용한 경우 0을 반환합니다. 오류가 발생하는 경우 1에서 6까지의 숫자를 반환합니다.  
  
## 참고 항목  
 [Visual Studio 설치](../Topic/Installing%20Visual%20Studio%202015.md)