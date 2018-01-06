---
title: "방법: 시각화 도우미 설치 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- debugger, visualizers
- visualizers, installing
ms.assetid: 3310ef43-515c-4d97-b0f9-51047247d3da
caps.latest.revision: "26"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 71b1d5cda498f42383e430a505296b2c4e074b73
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-install-a-visualizer"></a>방법: 시각화 도우미 설치
시각화 도우미를 만든 후에는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 사용할 수 있도록 이 시각화 도우미를 설치해야 합니다. 시각화 도우미를 설치하는 과정은 간단합니다.  
  
> [!NOTE]
>  **저장소** 앱만 표준 텍스트, HTML, XML 및 JSON 시각화 도우미는 지원 합니다. 사용자가 만든 사용자 지정 시각화 도우미는 지원되지 않습니다.  
  
### <a name="to-install-a-visualizer"></a>시각화 도우미를 설치하려면  
  
1.  빌드한 시각화 도우미가 들어 있는 DLL을 찾습니다.  
  
2.  이 DLL을 다음 위치 중 한 곳에 복사합니다.  
  
    -   *VisualStudioInstallPath*`\Common7\Packages\Debugger\Visualizers`  
  
    -   `My Documents\`*VisualStudioVersion*`\Visualizers`  
  
3.  원격 디버깅에 관리되는 시각화 도우미를 사용하려면 원격 컴퓨터의 동일한 경로에 DLL을 복사합니다.  
  
4.  디버깅 세션을 다시 시작합니다.  
  
## <a name="see-also"></a>참고 항목  
 [사용자 지정 시각화 도우미 만들기](../debugger/create-custom-visualizers-of-data.md)   
 [방법: 시각화 도우미 작성](../debugger/how-to-write-a-visualizer.md)