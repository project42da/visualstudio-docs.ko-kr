---
title: "서비스 참조 구성 대화 상자 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "msvse_wcf.dlg.ConfigureServiceReference"
helpviewer_keywords: 
  - "WCF 서비스, 서비스 참조 구성 대화 상자"
  - "서비스 참조[Visual Studio], 동작 구성"
  - "서비스 참조 구성 대화 상자"
ms.assetid: 25e4c36b-2db6-4e71-9010-b7068255d09d
caps.latest.revision: 16
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 서비스 참조 구성 대화 상자
**서비스 참조 구성** 대화 상자를 사용하면 [!INCLUDE[vsindigo](../data-tools/includes/vsindigo_md.md)] 서비스의 동작을 구성할 수 있습니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 도구 메뉴에서 설정 가져오기 및 내보내기를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
 **서비스 참조 구성** 대화 상자에 액세스하려면 **솔루션 탐색기**에서 서비스 참조를 마우스 오른쪽 단추로 클릭하고 **서비스 참조 구성**을 선택합니다.  [Add Service Reference Dialog Box](../Topic/Add%20Service%20Reference%20Dialog%20Box.md)에서 **고급** 단추를 클릭하여 대화 상자에 액세스할 수도 있습니다.  
  
## 작업 목록  
  
-   WCF 서비스가 호스팅되는 주소를 변경하려면 **주소** 필드에 새 주소를 입력합니다.  
  
-   WCF 클라이언트에서 클래스의 액세스 수준을 변경하려면 **생성된 클래스에 대한 액세스 수준** 목록에서 액세스 수준 키워드를 선택합니다.  
  
-   WCF 서비스의 메서드를 비동기적으로 호출하려면 **비동기 작업 생성** 확인란을 선택합니다.  
  
-   WCF 클라이언트에서 메시지 계약 형식을 생성하려면 **항상 메시지 계약 생성** 확인란을 선택합니다.  
  
-   WCF 클라이언트에 대해 목록 또는 사전 컬렉션 형식을 지정하려면 **컬렉션 형식** 및 **사전 컬렉션 형식** 목록에서 형식을 선택합니다.  
  
-   형식 공유를 사용하지 않도록 설정하려면 **참조된 어셈블리의 형식 재사용** 확인란의 선택을 취소합니다.  일부 참조된 어셈블리에 대해 형식 공유를 사용하도록 설정하려면 **참조된 어셈블리의 형식 재사용** 확인란을 선택하고, **참조된 어셈블리 중 지정된 어셈블리의 형식 재사용**을 선택한 후 **참조된 어셈블리 목록**에서 원하는 참조를 선택합니다.  
  
## UI 요소 목록  
 **Address**  
 서비스 참조가 서비스를 검색하는 웹 주소를 업데이트하는 데 사용됩니다.  예를 들어 개발 도중 서비스를 개발 서버에서 호스팅하다가 나중에 프로덕션 서버로 이동하여 주소를 변경해야 하는 경우가 이에 해당할 수 있습니다.  
  
> [!NOTE]
>  Address 요소는 [Add Service Reference Dialog Box](../Topic/Add%20Service%20Reference%20Dialog%20Box.md)에서 **서비스 참조 구성** 대화 상자가 표시된 경우에는 사용할 수 없습니다.  
  
 **생성된 클래스에 대한 액세스 수준**  
 WCF 클라이언트 클래스에 대한 코드 액세스 수준을 결정합니다.  
  
> [!NOTE]
>  웹 사이트 프로젝트의 경우 이 옵션은 항상 `Public`으로 설정되며 변경할 수 없습니다.  자세한 내용은 [Troubleshooting Service References](../data-tools/troubleshooting-service-references.md)을 참조하세요.  
  
 **비동기 작업 생성**  
 WCF 서비스 메서드를 동기적으로\(기본값\) 호출할지 아니면 비동기적으로 호출할지를 결정합니다.  
  
 **작업 기반 작업 생성**  
 비동기 코드를 작성하는 경우 이 옵션을 사용하면 .Net 4에 도입된 TPL\(작업 병렬 라이브러리\)을 활용할 수 있습니다.  [TPL\(작업 병렬 라이브러리\)](http://msdn.microsoft.com/library/dd460717.aspx)을 참조하세요.  
  
 **항상 메시지 계약 생성**  
 WCF 클라이언트에 대해 메시지 계약 형식을 생성할지 여부를 결정합니다.  메시지 계약에 대한 자세한 내용은 [메시지 계약 사용](../Topic/Using%20Message%20Contracts.md)을 참조하세요.  
  
 **컬렉션 형식**  
 WCF 클라이언트에 대한 목록 컬렉션 형식을 지정합니다.  기본 형식은 <xref:System.Array>입니다.  
  
 **사전 컬렉션 형식**  
 WCF 클라이언트에 대한 사전 컬렉션 형식을 지정합니다.  기본 형식은 <xref:System.Collections.Generic.Dictionary%602>입니다.  
  
 **참조된 어셈블리의 형식 재사용**  
 서비스가 추가 또는 업데이트되면 WCF 클라이언트에서 새 형식을 생성하는 대신 참조된 어셈블리에 이미 있는 형식을 다시 사용하도록 할지 여부를 결정합니다.  기본적으로 이 옵션은 선택되어 있습니다.  
  
 **모든 참조된 어셈블리의 형식 재사용**  
 선택하는 경우 **참조된 어셈블리 목록**의 모든 형식이 다시 사용됩니다\(가능한 경우\).  기본적으로 이 옵션이 선택됩니다.  
  
 **참조된 어셈블리 중 지정된 어셈블리의 형식 재사용**  
 선택하는 경우 **참조된 어셈블리 목록**에서 선택한 형식만 다시 사용됩니다.  
  
 **참조된 어셈블리 목록**  
 프로젝트 또는 웹 사이트의 참조된 어셈블리 목록을 포함합니다.  **참조된 어셈블리 중 지정된 어셈블리의 형식 재사용**을 선택하는 경우 개별 어셈블리를 선택하거나 선택을 취소할 수 있습니다.  
  
 **웹 참조 추가**  
 [NIB: Add Web Reference Dialog Box](http://msdn.microsoft.com/ko-kr/bdf05776-c591-40af-bfd7-e1e2aa1e87b5)를 표시합니다.  
  
> [!NOTE]
>  이 옵션은 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 2.0 버전을 대상으로 하는 프로젝트에만 사용해야 합니다.  
  
> [!NOTE]
>  **웹 참조 추가** 단추는 [Add Service Reference Dialog Box](../Topic/Add%20Service%20Reference%20Dialog%20Box.md)에서 **서비스 참조 구성** 대화 상자가 표시되는 경우에만 사용할 수 있습니다.  
  
## 참고 항목  
 [Add Service Reference Dialog Box](../Topic/Add%20Service%20Reference%20Dialog%20Box.md)   
 [How to: Add, Update, or Remove a Service Reference](../Topic/How%20to:%20Add,%20Update,%20or%20Remove%20a%20Service%20Reference.md)   
 [How to: Add a Reference to a Web Service](../Topic/How%20to:%20Add%20a%20Reference%20to%20a%20Web%20Service.md)   
 [Windows Communication Foundation 서비스 및 WCF Data Services](../data-tools/configure-service-reference-dialog-box.md)   
 [ASMX 및 WCF 서비스 사용 샘플](http://msdn.microsoft.com/ko-kr/788ddf2c-2ac1-416b-8789-2fbb1e29b8fe)