---
title: "VS Shell 배포 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: be8f2ffe-a322-4ac0-9c9e-873bd28e5d5e
caps.latest.revision: "2"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: e7632b99d3fa9d347b5a259cd446edc2f6d9efa8
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
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