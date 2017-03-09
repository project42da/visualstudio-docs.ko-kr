---
title: "How to: Add, Update, or Remove a WCF Data Service Reference | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "service references [Visual Studio]"
  - "WCF Data Service reference"
  - "WCF data service references"
  - "ADO.NET service references"
  - "ADO.NET Data Service reference"
ms.assetid: 892ebf37-3af4-472e-8744-92837677d611
caps.latest.revision: 11
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# How to: Add, Update, or Remove a WCF Data Service Reference
*서비스 참조*를 사용하면 프로젝트에서 하나 이상의 [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)]에 액세스할 수 있습니다.  **서비스 참조 추가** 대화 상자를 사용하여 현재 솔루션, 로컬 컴퓨터, LAN 또는 인터넷에서 [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)]를 검색할 수 있습니다.  
  
 [!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
## 서비스 참조 추가  
  
#### 외부 서비스에 대한 참조를 추가하려면  
  
1.  **솔루션 탐색기**에서 서비스를 추가할 프로젝트의 이름을 마우스 오른쪽 단추로 클릭한 다음 **서비스 참조 추가**를 클릭합니다.  
  
     **서비스 참조 추가** 대화 상자가 나타납니다.  
  
2.  **주소** 상자에 서비스의 URL을 입력한 다음 **이동**을 클릭하여 서비스를 검색합니다.  서비스에서 사용자 이름 및 암호 보안을 구현하는 경우 사용자 이름과 암호를 입력하라는 메시지가 나타날 수 있습니다.  
  
    > [!NOTE]
    >  신뢰할 수 있는 소스의 서비스만 참조해야 합니다.  신뢰할 수 없는 소스의 참조를 추가하면 보안상 위험할 수 있습니다.  
  
     **주소** 목록에서 URL을 선택할 수도 있습니다. 이 목록에는 올바른 서비스 메타데이터가 검색된 이전 URL 15개가 저장됩니다.  
  
     검색을 수행하는 동안에는 진행률 표시줄이 표시되며  언제든지 **중지**를 클릭하여 검색을 중지할 수 있습니다.  
  
3.  **서비스** 목록에서 사용할 서비스의 노드를 확장한 후 엔터티 집합을 선택합니다.  
  
4.  참조에 사용할 네임스페이스를 **네임스페이스** 상자에 입력합니다.  
  
5.  **확인**을 클릭하여 프로젝트에 참조를 추가합니다.  
  
     서비스 클라이언트\(프록시\)가 생성되고 해당 서비스를 설명하는 메타데이터가 app.config 파일에 추가됩니다.  
  
#### 현재 솔루션에 있는 서비스에 대한 참조를 추가하려면  
  
1.  **솔루션 탐색기**에서 서비스를 추가할 프로젝트의 이름을 마우스 오른쪽 단추로 클릭한 다음 **서비스 참조 추가**를 클릭합니다.  
  
     **서비스 참조 추가** 대화 상자가 나타납니다.  
  
2.  **검색**을 클릭합니다.  
  
     현재 솔루션의 모든 서비스\([!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)] 및 WCF 서비스\)가 **서비스** 목록에 추가됩니다.  
  
3.  **서비스** 목록에서 사용할 서비스의 노드를 확장한 후 엔터티 집합을 선택합니다.  
  
4.  참조에 사용할 네임스페이스를 **네임스페이스** 상자에 입력합니다.  
  
5.  **확인**을 클릭하여 프로젝트에 참조를 추가합니다.  
  
     서비스 클라이언트\(프록시\)가 생성되고 해당 서비스를 설명하는 메타데이터가 app.config 파일에 추가됩니다.  
  
## 서비스 참조 업데이트  
 [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)]의 엔터티 데이터 모델은 변경될 수 있습니다.  이 경우 서비스 참조를 업데이트해야 합니다.  
  
#### 서비스 참조를 업데이트하려면  
  
-   **솔루션 탐색기**에서 서비스 참조를 마우스 오른쪽 단추로 클릭한 다음 **서비스 참조 업데이트**를 클릭합니다.  
  
     원래 위치에서 참조를 업데이트하는 동안 진행률 대화 상자가 표시되고, 메타데이터 변경 사항을 모두 반영하도록 서비스 클라이언트가 다시 생성됩니다.  
  
## 서비스 참조 제거  
 더 이상 사용하지 않는 서비스 참조는 솔루션에서 제거할 수 있습니다.  
  
#### 서비스 참조를 제거하려면  
  
-   **솔루션 탐색기**에서 서비스 참조를 마우스 오른쪽 단추로 클릭한 다음 **삭제**를 클릭합니다.  
  
     솔루션에서 서비스 클라이언트가 제거되고 해당 서비스를 설명하는 메타데이터가 app.config 파일에서 제거됩니다.  
  
    > [!NOTE]
    >  삭제한 서비스 참조를 사용하는 모든 코드는 직접 제거해야 합니다.  
  
## 참고 항목  
 [Add Service Reference Dialog Box](../Topic/Add%20Service%20Reference%20Dialog%20Box.md)