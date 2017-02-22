---
title: "VS 셸 배포 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-tfs-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: be8f2ffe-a322-4ac0-9c9e-873bd28e5d5e
caps.latest.revision: 2
caps.handback.revision: 2
author: "alancameronwills"
ms.author: "awills"
manager: "douge"
---
# VS 셸 배포
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

어떤 Visual Studio 결정할 수 있습니다는 격리 셸 기능이 필요한 도메인\-특정 언어 및 해당 솔루션의 모양을 상호 작용 합니다.  Visual Studio 격리 셸에 대 한 자세한 내용은 참조 하십시오. [격리 된 셸 사용자 지정](../extensibility/customizing-the-isolated-shell.md).  격리 셸을 사용자 지정 하는 방법에 대 한 자세한 정보를 찾을 수 있습니다 [Customizing the Isolated Shell](http://msdn.microsoft.com/ko-kr/d75463cd-1155-42e4-8b7a-046ed6becbbf).  
  
### 배포 대상으로 Visual Studio 셸 설정  
  
1.  에 있는 **DslPackage** 프로젝트 열기 **source.extension.tt**.  
  
2.  아래에서 `<SupportedProducts>` 를 삽입 합니다.  
  
    ```  
    <IsolatedShell Version="1.0">MyIsolatedShell</IsolatedShell>  
    ```  
  
     대체  *MyIsolatedShell* 격리 셸 패키지의 이름입니다.