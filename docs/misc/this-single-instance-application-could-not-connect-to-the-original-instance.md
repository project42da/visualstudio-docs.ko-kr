---
title: "이 단일 인스턴스 응용 프로그램을 원본 인스턴스에 연결할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbrAppModel_SingleInstanceCantConnect"
ms.assetid: 7c2c0cee-02a1-4157-be03-39d18e18408f
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 이 단일 인스턴스 응용 프로그램을 원본 인스턴스에 연결할 수 없습니다.
이 단일 인스턴스 응용 프로그램을 원본 인스턴스에 연결할 수 없습니다. 이 문제가 발생할 수 있는 몇 가지 원인은 다음과 같습니다.  
  
-   원래 인스턴스의 응답이 중지되었습니다.  
  
-   커널 개체를 만들 수 있는 권한이 응용 프로그램에 없습니다. 커널 개체에 대한 자세한 내용은 [Mutexes](../Topic/Mutexes.md)를 참조하세요.  
  
     커널 개체의 기본 이름은 어셈블리의 GUID, 주 버전 번호 및 부 버전 번호를 연결하여 만들어집니다. 예를 들어 기본 이름은 `3639f15d-9547-43da-8145-60da347829915.1`일 수 있습니다.  
  
### 응용 프로그램을 개발할 때 이 오류를 해결하려면  
  
1.  응용 프로그램이 응답하지 않는 상태로 전환되지 않는지 확인합니다.  
  
2.  응용 프로그램에 커널 개체를 만들 수 있는 권한이 있는지 확인합니다.  
  
3.  응용 프로그램의 원래 인스턴스를 다시 시작합니다.  
  
4.  컴퓨터를 다시 시작하여 원래 인스턴스 응용 프로그램에 연결하는 데 필요한 리소스를 사용 중일 수 있는 프로세스를 지웁니다.  
  
5.  오류가 발생한 상황을 파악하여 Microsoft 기술 지원 서비스에 전화로 문의합니다.  
  
## 참고 항목  
 [NIB: 방법: 응용 프로그램에 대한 인스턴스 만들기 동작 지정\(Visual Basic\)](http://msdn.microsoft.com/ko-kr/48539ad8-d960-4210-beab-ee65f6c6dc6e)   
 [디버거 기본 사항](../debugger/debugger-basics.md)   
 [PAVEOVER 제품 기술 지원 및 접근성](http://msdn.microsoft.com/ko-kr/14e1d293-7b6d-40a6-bf3e-a92f8ee6c88c)