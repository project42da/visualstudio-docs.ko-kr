---
title: "방법: 서비스의 데이터에 연결 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "aspx"
helpviewer_keywords: 
  - "데이터[Visual Studio], 웹 서비스에 연결"
  - "데이터[Visual Studio], 웹 서비스에서 읽기"
  - "데이터 소스, 웹 서비스에서 만들기"
  - "데이터 읽기, 웹 서비스에서"
  - "웹 서비스, 데이터 소스"
  - "웹 서비스, 연결"
  - "웹 서비스, 데이터 읽기"
ms.assetid: a6b54353-05fe-4e5c-8631-90231fc95504
caps.latest.revision: 32
caps.handback.revision: 30
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 서비스의 데이터에 연결
[데이터 소스 구성 마법사](../data-tools/media/data-source-configuration-wizard.png)를 실행하고 **데이터 소스 형식 선택** 페이지에서 **서비스**를 선택하여 서비스에서 반환한 데이터에 응용 프로그램을 연결합니다.  
  
 마법사를 완료하면 서비스 참조가 프로젝트에 추가되어 즉시 [데이터 소스 창](../Topic/Data%20Sources%20Window.md)에서 사용할 수 있게 됩니다.  
  
> [!NOTE]
>  **데이터 소스** 창에 표시되는 항목은 서비스에서 반환하는 정보에 따라 달라집니다.  일부 서비스는 **데이터 소스 구성 마법사**가 바인딩할 수 있는 개체를 만드는 데 필요한 정보를 충분히 제공하지 않을 수도 있습니다.  예를 들어, 서비스에서 형식화되지 않은 데이터 집합을 반환하면 마법사가 완료될 때 **데이터 소스 창**에 아무런 항목도 표시되지 않습니다.  이것은 형식화되지 않은 데이터 집합이 스키마를 제공하지 않아 마법사가 데이터 소스를 만드는 데 필요한 정보를 충분히 갖지 못하기 때문입니다.  
  
 [!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
### 응용 프로그램을 서비스에 연결하려면  
  
1.  **데이터** 메뉴에서 **새 데이터 소스 추가**를 클릭합니다.  
  
2.  **데이터 소스 형식 선택** 페이지에서 **서비스**를 선택하고 **다음**을 클릭합니다.  
  
3.  사용할 서비스의 주소를 입력하거나 **검색**을 클릭하여 현재 솔루션에서 서비스를 찾은 다음 **이동**을 클릭합니다.  
  
4.  기본값 대신 새 **네임스페이스**가 입력될 수도 있습니다.  
  
    > [!NOTE]
    >  **고급**을 클릭하여 [서비스 참조 구성 대화 상자](../data-tools/configure-service-reference-dialog-box.md)를 엽니다.  
  
5.  **확인**을 클릭하여 프로젝트에 서비스 참조를 추가합니다.  
  
6.  **마침**을 클릭합니다.  
  
     데이터 소스가 **데이터 소스** 창에 추가됩니다.  
  
## 다음 단계  
  
#### 응용 프로그램에 기능을 추가하려면  
  
-   **데이터 소스** 창에서 항목을 선택한 다음 폼으로 끌어 와 바인딩된 컨트롤을 만듭니다.  자세한 내용은 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)을 참조하십시오.  
  
## 참고 항목  
 [연습: WCF 데이터 서비스에 WPF 컨트롤 바인딩](../data-tools/bind-wpf-controls-to-a-wcf-data-service.md)   
 [연습: WCF 데이터 서비스에 Silverlight 컨트롤 바인딩](../Topic/Walkthrough:%20Binding%20Silverlight%20Controls%20to%20a%20WCF%20Data%20Service.md)   
 [Windows Communication Foundation Services and WCF Data Services in Visual Studio](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md)