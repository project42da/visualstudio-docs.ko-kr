---
title: "방법: 스크립트 문서 보기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Script Explorer
ms.assetid: 8b621e53-4508-4b4a-9995-70995b0b9ac8
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 7daecd0974abd5be733e7cec3426045c1f859eb8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-view-script-documents"></a>방법: 스크립트 문서 보기
이전 버전의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서는 서버 쪽 스크립트에서 생성된 클라이언트 쪽 스크립트 파일이 스크립트 탐색기 창에 나타납니다. 스크립트 탐색기 창은 종종 숨겨지므로 클라이언트 쪽 스크립트를 사용할 수 있는지 확인할 수 없는 경우도 있습니다.  
  
 [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)]에서는 서버 쪽 스크립트에서 생성된 클라이언트 쪽 스크립트 파일이 솔루션 탐색기에 나타납니다. 솔루션 탐색기는 기본적으로 표시됩니다. 스크립트 탐색기 창은 사용되지 않습니다.  
  
 클라이언트 쪽 스크립트 파일은 디버그 모드나 중단 모드에서만 표시되며 에 표시 되는 **스크립트 문서** 노드.  
  
 서버 쪽 스크립트 파일은 항상 표시되며 에 표시 되는  **\<웹 사이트 경로 이름 >** 노드. 노드 이름에는이 예제를 비슷합니다.`c:\...\Website2\`  
  
### <a name="to-view-a-server-side-script-document"></a>서버 쪽 스크립트 문서를 보려면  
  
1.  **솔루션 탐색기**열고는  **\<웹 사이트 경로 이름 >** 노드.  
  
2.  보려는 스크립트 파일을 두 번 클릭합니다.  
  
     서버 쪽 스크립트 파일이 소스 창에 열립니다.  
  
### <a name="to-view-a-client-side-script-document"></a>클라이언트 쪽 스크립트 문서를 보려면  
  
1.  **솔루션 탐색기**열고는 **스크립트 문서** 노드.  
  
2.  보려는 스크립트 파일을 두 번 클릭합니다.  
  
     클라이언트 쪽 스크립트 파일이 소스 창에서 열립니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버거에서 데이터 보기](../debugger/viewing-data-in-the-debugger.md)