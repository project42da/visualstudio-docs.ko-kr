---
title: "VS Shell 배포 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: cbd972609f06f9ce7d3a7745b33b8d0d78dcad2e
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2018
---
# <a name="vs-shell-deployment"></a>VS 셸 배포
격리 셸을 사용 하는 Visual Studio를 결정할 수 도메인 특정 언어 및 해당 솔루션이 표시 되는 방식을와 상호 작용 해야 하는 기능입니다. Visual Studio 격리 셸에 대 한 자세한 내용은 참조 [격리 셸 사용자 지정](../extensibility/customizing-the-isolated-shell.md)합니다. 격리 셸에 사용자 지정 하는 방법에 대 한 자세한 정보를 찾을 수 [격리 셸 사용자 지정](http://msdn.microsoft.com/en-us/d75463cd-1155-42e4-8b7a-046ed6becbbf)합니다.  
  
### <a name="to-set-a-visual-studio-shell-as-the-deployment-target"></a>Visual Studio Shell 배포 대상으로 설정 하려면  
  
1.  에 **DslPackage** 프로젝트, 열기 **source.extension.tt**합니다.  
  
2.  `<SupportedProducts>` 삽입:  
  
    ```  
    <IsolatedShell Version="1.0">MyIsolatedShell</IsolatedShell>  
    ```  
  
     대체 *MyIsolatedShell* 격리 셸 패키지의 이름으로 합니다.