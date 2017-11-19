---
title: "방법: 가져오기 디자이너를 사용 하 여 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Activities.Presentation.View.ImportDesigner.UI
ms.assetid: 61328ab6-9b66-4e12-8630-22e30ee8c9d1
caps.latest.revision: "10"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8d6e530a82c1edfa221203b6c99f06151fe901af
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-use-the-imports-designer"></a>방법: 가져오기 디자이너 사용
가져오기 디자이너를 사용하여 식에서 사용할 형식의 네임스페이스를 입력할 수 있습니다. 과 거의 동일한는 **가져옵니다** 또는 **를 사용 하 여** Visual Basic.NET 및 C#, 가져오기 디자이너에 네임 스페이스 지정 키워드를 사용 하 간단히 식 대신에 정규화 된 형식 이름을 입력할 수 있습니다 버전 형식 이름입니다.  
  
 가져오기 디자이너에는 UI의 변경 내용과 워크플로 저장 시 변경 내용이 모두 적용됩니다. 워크플로가 저장되면 가져오기 디자이너에 네임스페이스를 자동으로 추가할 수 있습니다. 이러한 요구 사항은 다음과 같습니다.  
  
-   변수 및 인수 선언에 사용된 형식의 네임스페이스  
  
-   식에 사용된 형식의 네임스페이스  
  
-   워크플로 serialize에 필요한 그 밖의 네임스페이스(예: 워크플로에 배치된 사용자 지정 활동에서 사용되는 네임스페이스)  
  
 앞의 목록에서 설명한 논리로 인해 워크플로를 저장할 때 수동으로 삭제한 일부 네임스페이스가 가져오기 디자이너에 자동으로 다시 추가될 수 있습니다.  
  
### <a name="to-add-a-namespace-to-the-list-of-imported-namespaces"></a>가져온 네임스페이스 목록에 네임스페이스를 추가하려면  
  
1.  재호스트된 워크플로 응용 프로그램이나 [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)]의 WCF 워크플로 서비스 응용 프로그램, 워크플로 콘솔 응용 프로그램 또는 활동 라이브러리 프로젝트를 엽니다.  
  
2.  클릭 **Imports** 기본 캔버스 맨 아래에 있습니다. 가져오기 디자이너가 나타납니다.  
  
3.  가져오기 디자이너 맨 위에 있는 드롭다운 목록 컨트롤에서 네임스페이스를 입력하거나 선택합니다.  
  
     입력할 때 입력한 문자와 일치하는 유효한 네임스페이스 목록이 나타납니다.  
  
4.  키를 눌러 **Enter** 네임 스페이스 목록에 추가 합니다.  
  
5.  네임 스페이스 목록에서 제거 하려는 경우 네임 스페이스를 선택 하 고 다음 키를 누릅니다는 **삭제** 키보드의 키입니다. 네임스페이스가 들어 있는 어셈블리를 프로젝트에서 더 이상 참조할 수 없는 경우처럼 네임스페이스가 어떤 이유로 유효하지 않은 경우에만 네임스페이스를 삭제할 수 있습니다.