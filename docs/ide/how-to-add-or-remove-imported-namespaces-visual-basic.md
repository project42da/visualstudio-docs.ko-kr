---
title: "방법: 가져온 네임스페이스 추가 또는 제거(Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "가져온 네임스페이스 추가"
  - "가져온 네임스페이스[Visual Studio]"
  - "네임스페이스[Visual Studio], 가져오기"
  - "참조[Visual Studio], 가져온 네임스페이스"
  - "가져온 네임스페이스 제거"
ms.assetid: 44cebec3-0ea0-47c2-8406-4edeab6a997e
caps.latest.revision: 11
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 11
---
# 방법: 가져온 네임스페이스 추가 또는 제거(Visual Basic)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

네임스페이스 가져오기를 사용하면 요소를 자세히 지정하지 않고도 해당 네임스페이스의 요소를 코드에 사용할 수 있습니다.  예를 들어, `System.Messaging.MessageQueue` 클래스의 `Create` 메서드에 액세스하려는 경우 `System.Messaging` 네임스페이스를 가져오고 필요한 요소를 코드에서 `MessageQueue.Create`로 참조하기만 하면 됩니다.  
  
 가져온 네임스페이스는 **프로젝트 디자이너**의 **참조** 페이지에서 관리됩니다.  이 대화 상자에 지정한 가져오기는 컴파일러\(`/imports`\)에 직접 전달되어 프로젝트의 모든 파일에 적용됩니다.  하나의 소스 코드 파일에 네임스페이스를 사용하려면 `Imports` 문을 사용합니다.  
  
### 가져온 네임스페이스를 추가하려면  
  
1.  **솔루션 탐색기**에서 프로젝트의 **My Project** 노드를 두 번 클릭합니다.  
  
2.  **프로젝트 디자이너**에서 **참조** 탭을 클릭합니다.  
  
3.  **가져온 네임스페이스** 목록에서 추가할 네임스페이스에 대한 확인란을 선택합니다.  
  
    > [!NOTE]
    >  네임스페이스를 가져오려면 네임스페이스가 참조된 구성 요소에 있어야 합니다.  네임스페이스가 목록에 없으면 네임스페이스가 포함된 구성 요소에 대한 참조를 추가해야 합니다.  자세한 내용은 [방법: 참조 추가 대화 상자를 사용하여 참조 추가 또는 제거](http://msdn.microsoft.com/ko-kr/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)을 참조하십시오.  
  
### 가져온 네임스페이스를 제거하려면  
  
1.  **솔루션 탐색기**에서 프로젝트의 **My Project** 노드를 두 번 클릭합니다.  
  
2.  **프로젝트 디자이너**에서 **참조** 탭을 클릭합니다.  
  
3.  **가져온 네임스페이스** 목록에서 제거할 네임스페이스에 대한 확인란의 선택을 취소합니다.  
  
## 사용자 가져오기  
 사용자 가져오기를 사용하면 전체 네임스페이스가 아닌 네임스페이스에 포함된 특정 클래스를 가져올 수 있습니다.  예를 들어, 응용 프로그램에 `Systems.Diagnostics` 네임스페이스에 대한 가져오기가 있지만 네임스페이스에 있는 `Debug` 클래스만 가져오려는 경우  `System.Diagnostics.Debug`를 사용자 가져오기로 지정한 다음 `System.Diagnostics`에 대한 가져오기를 제거할 수 있습니다.  
  
 나중에 `EventLog` 클래스가 필요해지면 `System.Diagnostics.EventLog`를 사용자 가져오기로 입력하고 업데이트 기능을 사용하여 `System.Diagnostics.Debug`를 덮어쓸 수 있습니다.  
  
#### 사용자 가져오기를 추가하려면  
  
1.  **솔루션 탐색기**에서 프로젝트의 **My Project** 노드를 두 번 클릭합니다.  
  
2.  **프로젝트 디자이너**에서 **참조** 탭을 클릭합니다.  
  
3.  **가져온 네임스페이스** 목록 아래의 텍스트 상자에 루트 네임스페이스를 포함하여 가져올 네임스페이스의 전체 이름을 입력합니다.  
  
4.  **사용자 가져오기 추가** 단추를 클릭하여 **가져온 네임스페이스** 목록에 네임스페이스를 추가합니다.  
  
    > [!NOTE]
    >  같은 가져오기를 두 번 추가할 수 없으므로 해당 네임스페이스가 이미 목록에 있으면 **사용자 가져오기 추가** 단추를 사용할 수 없습니다.  
  
#### 사용자 가져오기를 업데이트하려면  
  
1.  **솔루션 탐색기**에서 프로젝트의 **My Project** 노드를 두 번 클릭합니다.  
  
2.  **프로젝트 디자이너**에서 **참조** 탭을 클릭합니다.  
  
3.  **가져온 네임스페이스** 목록에서 변경할 네임스페이스를 선택합니다.  
  
4.  **가져온 네임스페이스** 목록 아래의 텍스트 상자에 새 네임스페이스 이름을 입력합니다.  
  
5.  **사용자 가져오기 업데이트** 단추를 클릭하여 **가져온 네임스페이스** 목록의 네임스페이스를 업데이트합니다.  
  
## 참고 항목  
 [프로젝트의 참조 관리](../ide/managing-references-in-a-project.md)