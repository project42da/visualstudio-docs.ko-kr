---
title: "Office의 스레딩 지원 | Microsoft Docs"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "여러 스레드[Visual Studio에서 Office 개발]"
  - "개체 모델[Visual Studio에서 Office 개발], 스레딩 지원"
  - "Office 응용 프로그램[Visual Studio에서 Office 개발], 스레딩 지원"
  - "스레딩[Visual Studio에서 Office 개발]"
ms.assetid: 810a6648-fece-4b43-9eb6-948d28ed2157
caps.latest.revision: 33
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 32
---
# Office의 스레딩 지원
  이 항목에서는 Microsoft Office 개체 모델에서 스레딩을 지원하는 방법을 설명합니다.  Office 개체 모델은 스레드로부터 안전하지 않지만 Office 솔루션에서는 여러 스레드를 사용하여 작업할 수 있습니다.  Office 응용 프로그램은 COM\(Component Object Model\) 서버입니다.  클라이언트에서 COM을 사용하여 임의의 스레드에 있는 COM 서버를 호출할 수 있습니다.  스레드로부터 안전하지 않은 COM 서버를 위하여 COM은 서버에서 논리 스레드가 항상 하나만 실행되도록 동시 호출을 serialize하는 메커니즘을 제공합니다.  이 메커니즘을 STA\(단일 스레드 아파트\) 모델이라고 합니다.  호출이 serialize되므로 서버가 사용되고 있거나 백그라운드 스레드에서 다른 호출을 처리하는 동안 호출자가 차단될 수 있습니다.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## 다중 스레드 사용에 필요한 지식  
 다중 스레드를 사용하여 작업하려면 다중 스레딩의 다음과 같은 측면에 대해 기본적으로 알고 있어야 합니다.  
  
-   Windows API  
  
-   COM 다중 스레드 개념  
  
-   동시성  
  
-   동기화  
  
-   마샬링  
  
 다중 스레딩에 대한 일반적인 내용은 [구성 요소에서 다중 스레딩](../Topic/Multithreading%20in%20Components.md)을 참조하십시오.  
  
 Office는 주 STA에서 실행됩니다.  이러한 사실을 알고 있으면 Office에서 여러 스레드를 사용하는 방법을 이해할 수 있습니다.  
  
## 기본 다중 스레딩 시나리오  
 Office 솔루션의 코드는 항상 주 UI 스레드에서 실행됩니다.  백그라운드 스레드에서 별도의 작업을 실행하여 응용 프로그램 성능을 개선할 수 있습니다.  두 작업을 차례로 완료하는 대신 거의 동시에 완료하는 것이 목적입니다. 이렇게 하면 좀더 원활하게 실행할 수 있는데 이것이 바로 다중 스레드를 사용하는 주된 이유입니다.  예를 들어, 주 Excel UI 스레드에 이벤트 코드가 있는 경우 서버에서 데이터를 수집하고 이 데이터를 사용하여 Excel UI의 셀을 업데이트하는 작업을 백그라운드 스레드에서 실행할 수 있습니다.  
  
## Office 개체 모델을 호출하는 백그라운드 스레드  
 백그라운드 스레드가 Office 응용 프로그램을 호출하면 호출은 STA 경계를 넘어 자동으로 마샬링됩니다.  그러나 백그라운드 스레드에서 호출을 생성할 때 Office 응용 프로그램에서 해당 호출을 처리할 수 있다는 보장은 없습니다.  다음과 같은 경우가 있을 수 있습니다.  
  
1.  호출이 시작되려면 Office 응용 프로그램에서 메시지를 펌프해야 합니다.  Excel에서 양보 없이 많은 처리 과정을 수행하는 경우 시간이 오래 걸릴 수 있습니다.  
  
2.  아파트에 다른 논리 스레드가 이미 있는 경우 새 스레드가 들어갈 수 없습니다.  논리 스레드가 Office 응용 프로그램에 들어간 다음 다시 호출자의 아파트에 대한 재진입 호출을 생성하는 경우에 이러한 상황이 자주 발생합니다.  응용 프로그램은 해당 호출이 반환될 때까지 차단됩니다.  
  
3.  Excel에서 들어오는 호출을 즉시 처리할 수 없는 경우가 있습니다.  예를 들어 Office 응용 프로그램에 모달 대화 상자가 표시되어 있는 경우가 이에 해당합니다.  
  
 위의 두 번째 및 세 번째 경우에서 COM은 [IMessageFilter](http://msdn.microsoft.com/ko-kr/e12d48c0-5033-47a8-bdcd-e94c49857248) 인터페이스를 제공합니다.  서버에서 이 인터페이스를 구현하면 모든 호출이 [HandleIncomingCall](http://msdn.microsoft.com/ko-kr/7e31b518-ef4f-4bdd-b5c7-e1b16383a5be) 메서드를 통해 진입합니다.  두 번째 경우에는 호출이 자동으로 거부됩니다.  세 번째 경우에는 서버에서 상황에 따라 호출을 거부할 수 있습니다.  호출이 거부될 경우 호출자는 수행할 작업을 결정해야 합니다.  일반적으로 호출자는 [IMessageFilter](http://msdn.microsoft.com/ko-kr/e12d48c0-5033-47a8-bdcd-e94c49857248)를 구현합니다. 이 경우 [RetryRejectedCall](http://msdn.microsoft.com/ko-kr/3f800819-2a21-4e46-ad15-f9594fac1a3d) 메서드에서 거부를 통보합니다.  
  
 하지만 Visual Studio의 Office 개발 도구를 사용하여 만든 솔루션의 경우에는 COM interop가 거부된 모든 호출을 <xref:System.Runtime.InteropServices.COMException>\("메시지 필터가 그 응용 프로그램이 사용 중이라고 표시하고 있습니다."\)으로 변환합니다.  백그라운드 스레드에서 개체 모델을 호출할 때마다 이 예외를 처리할 준비를 해야 합니다.  일반적으로 특정 시간 동안 재시도한 다음 대화 상자를 표시합니다.  그러나 백그라운드 스레드를 STA로 만든 다음 해당 스레드에서 이 경우를 처리하도록 메시지 필터를 등록할 수도 있습니다.  
  
## 올바른 스레드 시작  
 새 STA 스레드를 만들 때는 스레드를 시작하기 전에 아파트 상태를 STA로 설정합니다.  다음 코드 예제에서는 이 작업을 수행하는 방법을 보여 줍니다.  
  
 [!code-csharp[Trin_VstcoreCreatingExcel#5](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreCreatingExcel/CS/ThisWorkbook.cs#5)]
 [!code-vb[Trin_VstcoreCreatingExcel#5](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreCreatingExcel/VB/ThisWorkbook.vb#5)]  
  
 자세한 내용은 [Managed Threading Best Practices](../Topic/Managed%20Threading%20Best%20Practices.md)을 참조하십시오.  
  
## 모덜리스 폼  
 모덜리스 폼을 사용하면 폼이 표시되는 동안 응용 프로그램과 몇 가지 유형의 상호 작용을 할 수 있습니다.  사용자는 폼과 상호 작용하고, 폼은 닫히지 않은 상태로 응용 프로그램과 상호 작용합니다.  Office 개체 모델은 관리되는 모덜리스 폼을 지원하지만, 백그라운드 스레드에서는 이러한 폼을 사용하지 말아야 합니다.  
  
## 참고 항목  
 [구성 요소에서 다중 스레딩](../Topic/Multithreading%20in%20Components.md)   
 [Managed Threading](../Topic/Managed%20Threading.md)   
 [스레딩&#40;C&#35; 및 Visual Basic&#41;](../Topic/Threading%20(C%23%20and%20Visual%20Basic).md)   
 [Using Threads and Threading](../Topic/Using%20Threads%20and%20Threading.md)   
 [Office 솔루션 디자인 및 만들기](../vsto/designing-and-creating-office-solutions.md)  
  
  