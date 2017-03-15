---
title: "이 컴퓨터의 프록시 설정이 웹 검색에 적합하게 구성되지 않았습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.message.VB_E_MUSTSPECIFYPROXYSERVER"
  - "vs.WebDiscoveryProxyHelp"
ms.assetid: aea2cc20-9180-47cb-b1ed-78fa5f8a407f
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 이 컴퓨터의 프록시 설정이 웹 검색에 적합하게 구성되지 않았습니다.
방화벽 뒤에 있는 컴퓨터에서 개발할 때 프록시 서버가 Internet Explorer 연결 설정에 적합하게 명시적으로 지정되지 않은 경우 웹 참조 추가 대화 상자에 이 오류가 나타납니다. 방화벽 외부의 서비스를 웹 참조 추가 대화 상자의 웹 브라우저에서 사용할 수 있도록 하려면, 네트워크의 프록시 서버 주소나 포트를 명시적으로 지정해야 합니다. .NET Framework에서는 Internet Explorer 연결에 사용되는 프록시 자동 검색 옵션이 무시됩니다. 이 프록시 정보를 네트워크 관리자에게 문의해야 할 수 있습니다.  
  
 “방화벽 및 웹 프록시 클라이언트의 자동 검색”에 대한 자세한 내용은 [http:\/\/www.microsoft.com\/technet\/prodtechnol\/isa\/2004\/plan\/automaticdiscovery.mspx](http://www.microsoft.com/technet/prodtechnol/isa/2004/plan/automaticdiscovery.mspx)를 참조하세요.  
  
### Internet Explorer에서 프록시 서버를 지정하려면  
  
1.  **도구** 메뉴에서 **옵션**을 선택합니다.  
  
2.  **옵션** 대화 상자에서 **환경**을 선택한 다음 **웹 브라우저**를 선택합니다.  
  
3.  **Internet Explorer 옵션**을 클릭합니다.  
  
4.  **연결** 탭에서 **LAN 설정**을 클릭합니다.  
  
5.  **자동으로 설정 검색**의 선택을 취소합니다.  
  
6.  **프록시 서버** 영역에서 **사용자 LAN에 프록시 서버 사용\(이 설정은 전화 연결이나 VPN 연결에는 적용되지 않음\)**을 선택합니다.  
  
7.  사용 중인 네트워크와 일치하는 주소 및 포트 번호를 지정합니다.  
  
8.  **확인**, **확인**을 차례로 클릭한 다음 다시 **확인**을 클릭합니다.  
  
9. **파일** 메뉴에서 **끝내기**를 선택한 다음 Visual Studio를 다시 엽니다.  
  
## 참고 항목  
 [NIB: 웹 참조 추가 대화 상자](http://msdn.microsoft.com/ko-kr/bdf05776-c591-40af-bfd7-e1e2aa1e87b5)   
 [NIB: 방법: 웹 참조 추가 및 제거](http://msdn.microsoft.com/ko-kr/a7ddaa5d-4672-405b-91b3-39de65d7e3a2)   
 [Programming the Web with XML Web Services](http://msdn.microsoft.com/ko-kr/2d651a26-73df-4b39-85fa-7913a7d6bee4)